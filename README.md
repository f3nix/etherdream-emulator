EtherDream Graphical Emulator
=============================
This is a visual emulator for the
[EtherDream laser projector DAC](http://ether-dream.com/). It displays
the points that are projected in real time, making it easy for
development and debugging without actual laser hardware present.

This is currently in a working state and can be used for active
EtherDream / laser projection development.

Screenshot:

![Laser Pong Screenshot](http://i.imgur.com/RmySzdQ.png)

Installation and Use
--------------------
Install Rust version 1.13 or greater.

For Windows - tested under MSYS2 environment. Install freetype in
MSYS2 with: `pacman -S mingw-w64-x86_64-freetype` or 
`pacman -S mingw-w64-i686-freetype`. More info 
[here](https://github.com/PistonDevelopers/freetype-sys).

```
git clone https://github.com/echelon/etherdream-emulator.git
cd etherdream-emulator
cargo run
```

Or to compile and run the release version (faster and more performant),

```
cargo build --release
./target/release/etherdream-emulator
```

The emulator sends EtherDream broadcast packets and listens on the
default EtherDream port. Simply start sending traffic to it!

See Also
--------
Rust laser projection projects:

- [etherdream.rs](https://github.com/echelon/etherdream.rs), a Rust
  library for driving EtherDream.

- [ILDA.rs](https://github.com/echelon/ilda.rs), a Rust parser for the
  ILDA laser display format.

There are also a number of existing programs I've written that talk in
EtherDream, all of which can be "emulated" with this software:

- [Laser Asteroids](https://github.com/echelon/laser-asteroids),
  an EtherDream laser projector video game I wrote in Python for the
  Fall 2012 SPSU Game Jam.

- [Laser Pong](https://github.com/echelon/laser-pong),
  another EtherDream video game I wrote in Python during Summer 2013.

- [Untitled Game](https://github.com/lightengine/gamejam-demo), written
  for two laser projectors (and two EtherDream DACs) by myself and
  Scott Adams for the Fall 2013 SPSU Game Jam. It's quirky, but
  demonstrates multi-projection. Scott worked on the game while I worked
  on the network and graphics stack.

- [Laser Testbed](https://github.com/echelon/laser-testbed),
  which contains lots of my early testing with laser projection. There
  are dozens of animations, shapes, primitives, etc.

- [Laser Client](https://github.com/echelon/laser-client),
  which projects slides containing GML (Graffiti Markup Language) and
  poorly serialized SVG objects, which can be individually programmed
  with animation and 2D transformations. (The code is terrible.)

License
-------

**BSD 4-clause**

Copyright (c) 2016, Brandon Thomas. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.

3. All advertising materials mentioning features or use of this software
   must display the following acknowledgement:

   This product includes software developed by Brandon Thomas
   (bt@brand.io, echelon@gmail.com).

4. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY COPYRIGHT HOLDER "AS IS" AND ANY EXPRESS OR
IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL COPYRIGHT HOLDER BE LIABLE FOR ANY DIRECT,
INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT,
STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.

TODO
----
There are a number of future improvements to make:

- Add a gif or screenshot.
- Full protocol support (all commands, plus a better state machine)
- Unit tests
- Better error handling
- Better logging
- Support Multiprojection (multiple DACs/projectors)
- Draw on a 3D surface and calculate projection angles and deformations
