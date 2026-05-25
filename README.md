parachute-package
=================
This is a packaging build that puts together a distributable build of the following, on all the supported operating
systems we support:
* transputer-emulator
* transputer-macro-assembler
* transputer-eforth (in a forthcoming release)
* retro-c-compiler (maybe)
* transputer-k-r-c-compiler (in a forthcoming release)

It runs on:
* Apple macOS (Catalina on Intel (EOL), Tahoe on Apple Silicon)
* Windows 10  (EOL, but I don't have TPM hardware, so no Windows 11)
* Ubuntu 24.04 (EOL 2026-07-09)
* Raspberry Pi Debian 12 (EOL 30 June 2028).

In addition, the emulator component runs on:
* Raspberry Pi Pico 1 or 2

It is part of the [Parachute Project](https://devzendo.github.io/parachute).

(C) 2005-2026 Matt J. Gumbley
matt.gumbley@devzendo.org
@mattgumbley @devzendo
http://devzendo.github.io/parachute


Status
------
First release 0.0.1 Midsummer 2019 (19 June 2019).

In active development.

Roadmap
-------
Detailed roadmap for each component can be found in its own README.md, all of which are contained in this distribution.
The overall project roadmap is...

First release:
* Ported to macOS (El Capitan), Linux (Ubuntu 16.04, Ubuntu 18.04, CentOS 7.6, Raspbian Stretch), Windows 10.
* A Cross Platform system that can run "Hello World" (via my NodeServer implementation).

Second release:
* Change the NodeServer to be compatible with the Inmos compatible iServer protocol.
* Ported to macOS (Catalina, Tahoe), Linux (Ubuntu 24.04, Rasperry Pi Debian 12), Windows 10.
* Ported emulator to Raspberry Pi Pico 1 & 2.

Third release:
* Include eForth.

... who knows, after this?

Release Notes
-------------
-------------
Detailed release notes for each component can be found in its own README.md, all of which are contained in this
distribution. The overall project release notes are...

0.0.1 Midsummer 2019 - 21 June 2019
First release on all platforms, containing:
* transputer-emulator 0.0.1, with 'hello world'.
* transputer-macro-assembler 0.0.1


License
-------
This code is released under the Apache 2.0 License: http://www.apache.org/licenses/LICENSE-2.0.html.
(C) 2005-2026 Matt Gumbley, DevZendo.org


