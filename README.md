# parachute

**An open, simple and useful personal computing stack — built around the Transputer (in emulation).**

Parachute is a long-term project to build a small systems architecture from the ground up: emulator, toolchain, OS kernel, and applications — designed to run on cheap, widely available hardware, and small enough that a single person can understand the whole system.

## Why does this exist?

Modern computing systems have grown beyond anyone's full comprehension. Complex user interfaces with a bewildering mishmash of interface styles, labyrinthine internals, monolithic kernels, vast learning curves to surmount should you want to develop for them, and masses of library dependencies. Even expert engineers only ever understand a small part of the stack they build on. That wasn't always true — and it doesn't have to be, going forward. Small systems offer a solution.

Other retrocomputing platforms continue the development of existing 8- and 16-bit systems. The Transputer offers a different starting point: A simple 32-bit CPU with built-in support for multitasking, communication, and parallelism, it was designed around a proven model for describing systems as networks of parallel processes. Its language, occam, makes that structure explicit. A microkernel OS falls out of it almost naturally.

Distributing OS components across a cluster of Transputer nodes isn't an architectural trick — it's the architecture working as intended. Individual nodes are modest, but are connected in a network to the other nodes in the system. The components that run on each node are small, and easy to understand. 

## Inspiration

Parachute is guided by the ideas of people who believed software could be lean, comprehensible, and purposeful:

* **The Inmos Transputer, occam, and C.A.R. Hoare's CSP** — the technical foundation (with other languages)
* **Niklaus Wirth's Project Oberon** and his essay "_A Plea for Lean Software_" — a philosophy of restraint
* **The Amiga OS** — elegance and capability in a small footprint
* **Psion PDAs and the SIBO/EPOC operating systems** — productive, focused, astonishingly efficient
* **The Palm Pilot** — proof that constraints produce clarity

Think: the early Mac, the Amiga, early Windows — but parallel, distributed, and built on a CPU that was genuinely ahead of its time.

And remember the PDA? Pocket-sized. Days of battery life on AAs. Distraction-free and productive. The smartphone was not its natural successor. Touch screens are necessary, but not sufficient for productive work - proper keyboards are essential. 

## Goals

* **A portable, open-source Transputer emulator** — inspired by one I wrote years ago, rewritten for portability to the popular operating systems
* **Embedded on cheap, available hardware** — microcontrollers and single-board computers with small touch screens and optional keyboards
* **A toolchain** — assembler, Small-C, eForth, occam; enough to build real things
* **A distributed microkernel OS** — kernel, drivers, libraries, and a simple UI
* **The same applications run everywhere** — desktop emulator or embedded node, same software
* **Small. Simple. Understandable.** — if you can't read the whole system, it's already too big


## Who is this for?

Those who yearn for a return to simple, distraction-free devices, that won't become obsolete, due to them being buildable from open technology.

Developers and tinkerers who remember when personal computing felt like a frontier — or who wish they'd been there.

People who want to understand their tools all the way down.

Anyone who thinks the direction of travel in modern systems (more abstraction, more complexity, 
more magic, less freedom, no right-to-repair) isn't the only possible direction.


This is a community project as much as a technical one. _There's a lot to build. Come help._

---

## Sub-projects

Parachute is built from the following components, which are assembled together into each release:

| Sub-project | Description | Status |
|---|---|---|
| [transputer-emulator](transputer-emulator) | Cross-platform emulator and host/device interface daemons | Released |
| [transputer-macro-assembler](transputer-macro-assembler) | Macro assembler in the style of MASM, targeting the Transputer | Released |
| [transputer-eforth](transputer-eforth) | eForth language implementation | Forthcoming |
| [transputer-k-r-c-compiler](transputer-k-r-c-compiler) | Small-C compiler and assembler, written by Óscar Toledo Gutiérrez, translated from Spanish | Forthcoming |
| [retro-c-compiler](retro-c-compiler) | Embryonic C compiler | Exploratory |

Detailed documentation for each component lives in its own README.
 
---

## Platform Support

**Desktop**

| Platform                                                            | Notes                                  |
|---------------------------------------------------------------------|----------------------------------------|
| macOS Catalina (Intel)                                              | Supported - OS and architecture is EOL |
| macOS Tahoe (Apple Silicon)                                         | Supported                              |
| Windows 10                                                          | Supported; may work on 11, untested    |
| Ubuntu 24.04 / Linux Mint etc.                                      | Supported                              |
| Raspberry Pi Debian 12                                              | Supported                              |
| macOS El Capitan, Ubuntu 16.04, 18.04, CentOS 7.6, Raspbian Stretch | Obsolete                               |

**Embedded**

| Platform | Notes |
|---|---|
| Raspberry Pi Pico 1 | Supported |
| Cheap Yellow Display | Forthcoming |
 
---

## Status & Roadmap

Parachute is in active development. The first release appeared in June 2019; the project has grown steadily since.

**Release 0.0.1 — Midsummer 2019**
- Emulates an "integer T805" Transputer, that connects to a 'NodeServer' process providing access to host filesystem and console
- Ported to macOS El Capitan, Linux (Ubuntu 16.04/18.04, CentOS 7.6, Raspbian Stretch), and Windows 10
- Development tools: MASM-like macro assembler
- "Hello World" running end-to-end via the original NodeServer implementation

**Release 0.0.2** - In progress
- NodeServer's custom protocol replaced with an iServer-compatible implementation (iServer was Inmos' standard host server, providing boot/debug/IO facilities)
- Allows validation using Mike Brüstle's Transputer Validation Suite. Conformance: 46 instructions pass, 8 fail 
- "Hello World" now uses iServer protocol
- Better debug support for eForth
- Platform support modernised: macOS (Catalina, Tahoe), Linux (Ubuntu 24.04, Raspberry Pi Debian 12), Windows 10
- Emulator ported to Raspberry Pi Pico, with bit-banged (slow) GPIO link implementation, and one link and a diagnostic channel exposed over USB CDC serial
- An IServer link that can run over a TTY (Linux/macOS) or COM port (Windows) to connect to a Pi Pico emulator.
- Emulator can now operate its boot/peek/poke protocol from any link
- USB CDC to link adapter on Raspberry Pi Pico
- Known problem: The IServer's file handling does not yet prevent directory traversal vulnerabilities.

**Release 0.0.3** — Forthcoming
- More complete iServer implementation.
- eForth and Small-C compiler included
- Faster link implementation for the Raspberry Pi Pico using PIO

**Release 0.0.4** - Vision
- Complete integer Transputer emulation
- Port to the ESP-32 'Cheap Yellow Display'
- Inmos occam tools included
- Start of the OS and device drivers

**Beyond that** — who knows? Suggestions welcome!


## Download

All releases are available from the [Downloads](https://devzendo.github.io/parachute-download/) page.

## AI Declaration

I use Claude.ai occasionally for assistance; all its output is vetted thoroughly by me.

I gratefully acknowledge the work of others that was stolen without consent in the creation of Large
Language Models. I understand the environmental impact of this technology.

## License & Contact

Released under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0.html).

© 2005–2026 Matt Gumbley, [DevZendo.org](http://devzendo.github.io/parachute)

