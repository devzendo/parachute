parachute-package
=================
This is a packaging build that puts together a distributable build of the following, on all the operating systems we support:
* transputer-emulator
* transputer-macro-assembler
* transputer-eforth

It runs on Apple macOS (El Capitan+), Windows 10, CentOS 7.6, Ubuntu 16.04/18.04 and Raspbian Stretch.

It is part of the [Parachute Project](https://devzendo.github.io/parachute).

(C) 2005-2019 Matt J. Gumbley
matt.gumbley@devzendo.org
@mattgumbley @devzendo
http://devzendo.github.io/parachute


Status
------
In progress, April 2019. Modernising, building on modern macOS/Linux/Windows.

* Creating the packaging build, first on macOS.

Roadmap
-------
First release:
* Ported to macOS (El Capitan +), Linux (Ubuntu 16.04, Ubuntu 18.04, CentOS 7.6, Raspbian Stretch), Windows 10.
* A Cross Platform system that can run "Hello World" (via my NodeServer implementation).

Release Notes
-------------
0.01 (ongoing work for the first release)
* Versioning and build now controlled by Maven and CMake.
* Successfully runs hello2.asm !
* Renamed emulator binary from t800emul to temulate.
* Started adding the T801 instructions, from "Transputer Instruction Set - Appendix, Guy Harriman".
* Started adding the T801/T805 instructions from "Support for debugging/breakpointing in transputers" (INMOS
  Technical Note 61).
  Added the -j flag to enable 'j 0' breakpoints.
* Described current implementation/missing status in the above section.
* The T810 instructions from "The IMS T810 - A Preliminary Survey" are not implemented.
* Builds using Maven/CMake/CLion on macOS, Windows 10, CentOS 7, Ubuntu LTS, Raspbian Stretch.
* Added Boot-from-ROM, fixed Wdesc bug after boot from link.
* Fixes: xword, call, j & scheduling (with assistance from Michael Brüstle), locations of TPtrLoc1, TPtrLoc0.
  csngl and xdble: correct detection of sign of Areg
* Monitor: db (renamed from da), dw improvements, added w (workspace display), added b/b+b-/b? (breakpoints),
  added s (show all state).
* Adopted the Apache License v2.
* Since the assembler understands offset addressing, the manual building of offset operands has been changed from:
  j 'label - _XX1'
  _XX1:
  to:
  j label
  


License
-------
This code is released under the Apache 2.0 License: http://www.apache.org/licenses/LICENSE-2.0.html.
(C) 2005-2019 Matt Gumbley, DevZendo.org


