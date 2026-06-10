# parachute

**A modern, open, fully-understandable, useful personal computing stack — built around the Transputer (in emulation).**

Parachute is a long-term project to build a small systems architecture from the ground up: emulator, toolchain, OS kernel, and applications — designed to run on cheap, widely available hardware, and small enough that a single person can hold the whole thing in their head.

## Why does this exist?

Modern computing systems have grown beyond anyone's full comprehension. Monolithic kernels, opaque toolchains, and sprawling dependencies mean that even expert engineers only ever understand a thin slice of the stack they build on. That wasn't always true — and it doesn't have to be.

The Transputer offers a different starting point. A simple 32-bit CPU with built-in support for multitasking, communication, and parallelism, it was designed from the ground up around Hoare's Communicating Sequential Processes — a clean mathematical model for describing systems as networks of parallel processes. Its language, occam, makes that structure explicit. A microkernel OS falls out of it almost naturally.

Distributing OS components across a cluster of Transputer nodes isn't an architectural trick — it's the architecture working as intended. Individual nodes are modest. Connected in a pipeline or mesh, they can be capable. And crucially: every part of the system can be understood.

## Inspiration

Parachute stands on the shoulders of people who believed software could be lean, comprehensible, and purposeful:

* **The Inmos Transputer, occam, and CSP** — the technical foundation (with other languages)
* **Niklaus Wirth's Project Oberon** and his essay "_A Plea for Lean Software_" — a philosophy of restraint
* **The Amiga OS** — elegance and capability in a small footprint
* **Psion PDAs and the SIBO/EPOC operating systems** — productive, focused, astonishingly efficient
* **The Palm Pilot** — proof that constraints produce clarity

Think: the early Mac, the Amiga, early Windows — but parallel, distributed, and built on a CPU that was genuinely ahead of its time.

And remember the PDA? Pocket-sized. Days of battery life on AAs. Distraction-free and productive. The smartphone was not its natural successor.

## Goals

* **A portable, open-source Transputer emulator** — inspired by one I wrote years ago, rebuilt properly
* **Embedded on cheap, available hardware** — microcontrollers and single-board computers with small touch screens and optional keyboards
* **A toolchain** — assembler, Small-C, eForth, occam; enough to build real things
* **A distributed microkernel OS** — kernel, drivers, libraries, and a simple UI
* **The same applications run everywhere** — desktop emulator or embedded node, same binary
* **Small. Simple. Understandable.** — if you can't read the whole system, it's already too big


## Who is this for?

Developers and tinkerers who remember when personal computing felt like a frontier — or who wish they'd been there.
People who want to understand their tools all the way down.
Anyone who thinks the direction of travel in modern systems (more abstraction, more complexity, 
more magic, less freedom, no right-to-repair) isn't the only possible direction.

Those who yearn for a return to simple, distraction-free devices, that won't become obsolete, due to them being buildable from open technology.

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
| Raspberry Pi Pico 1 & 2 | Supported |
| Cheap Yellow Display | Forthcoming |
 
---

## Status & Roadmap

Parachute is in active development. The first release appeared in June 2019; the project has grown steadily since. Full roadmap details for each component are in their respective READMEs — the overall arc is:

**Release 0.0.1 — Midsummer 2019**
- Emulates an "integer T805" Transputer
- Ported to macOS El Capitan, Linux (Ubuntu 16.04/18.04, CentOS 7.6, Raspbian Stretch), and Windows 10
- "Hello World" running end-to-end via the original NodeServer implementation

**Release 0.0.2** - In progress
- NodeServer replaced with an iServer-compatible implementation
- Transputer Validation Suite conformance: 46 pass, 8 fail 
- "Hello World" now uses iServer protocol
- Platform support modernised: macOS (Catalina, Tahoe), Linux (Ubuntu 24.04, Raspberry Pi Debian 12), Windows 10
- Emulator ported to Raspberry Pi Pico, with bit-banged link implementation

**Release 0.0.3** — Forthcoming
- iServer improvements
- eForth and Small-C compiler included
- Faster link implementation for the Raspberry Pi Pico using PIO

**Release 0.0.4** - Vision
- Complete integer Transputer emulation
- Port to the 'Cheap Yellow Display'
- occam tools included
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

