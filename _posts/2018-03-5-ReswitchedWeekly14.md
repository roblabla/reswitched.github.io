---
layout: post
title: Reswitched Weekly 14
category: reswitchedweekly
---
Hello and welcome to Reswitched Weekly, a weekly summary of the progress
made by the reswitched team and wider community around homebrew development for
the Nintendo Switch.

We're doing two weeks for the price of one this time (again).We got sd card support and full c++ support.
## What happened
- @misson20000 fixed a number of bugs for nxodance. In doing so fixed c++ exceptions. Full c++ support has been merged.
- @misson20000 split ace_loader into 2 parts. wk_ace for cleaning up the browser and sysmod_ace for loading the NROs.
- There have been a number of changes to the build system
	- @dvdfreitag added rules to prevent building with root. For those who laugh this came up more than once.
	- @roblabla made MacOS users' life easier, by removing the requirement to add llvm's prefix to PATH. Libtransistor will now ask brew for the prefix on it's own.
	- @misson20000 cleaned up the build system for binary packaging.
	- @horicon added some fixes to the build system relating to clean up.
- @Roblabla made some big fixes were done to the WIP code generator of SwIPC
- @Roblabla made some fixes to Mephisto's fsp-srv emulation. Closed file handles will now get flushed to disk, and you can now call ReadDirectory.he also added support for loading KIPs in Mephisto.
- @Thog added some more BSD socket functions.
- @Roblabla added sd card support to libtransistor.
- All libraries and support files will be installed into dist/. LIBTRANSISTOR_HOME should point to this /path/to/libtransistor/dist directory, not the /path/to/libtransistor/ directory
See all the changes at [the latest prerelease][https://github.com/reswitched/libtransistor/releases/tag/v1.2.0-rc2]

## What people are working on
- @Roblabla is working on a standalone toolchain in rust. [repo](https://github.com/roblabla/megaton-hammer)
- binary distributions will be coming out soon
- @misson20000 has started working on a C++ api. [discussion here][https://github.com/reswitched/libtransistor/pull/123]

## Call for participation

Reswitched is always looking for people to work on the various projects. If you
want to give a helping hand, hop on the [Discord] so we can coordinate the work!

In the libtransistor department, a lot of things could be implemented without
much requirements beyond "knowing C". Below are a list of issues, of varying
difficulty, that we feel the community could help on. If you're interested in
working on those, but need some help, feel free to reach out to @roblabla on
Discord. I'll be glad to write some mentoring notes on what needs to be done,
and to guide you through the process.

- Documentation work!
  - Enhancing the libtransistor docs. You can take a look at
    [this issue](https://github.com/reswitched/libtransistor/issues/89).
  - SwIPC documentation. We need to make it *easy* for people to know what each
    function and service does.
- JIT API! The new hbl allows us to call svcMapProcessCodeMemory, meaning we can
  now JIT. We should make sure we have a proper API for this. Mimicking mprotect
  would probably be the best past, to be compatible with existing code.
- Joystick support in SDL2! If you want to pick this up, look at [this issue](https://github.com/reswitched/sdl-libtransistor/issues/1).
- Thread Local Storage. Check [this issue](https://github.com/reswitched/libtransistor/issues/91).
- Implementing more services into libtransistor. We're lacking a bunch of things
  like USB support and whatnot.
- Port apps and libraries. Make sure they work! We have graphics and audio, the
  sky is the limit!

## Next week...

If you're working on anything fun, please post on [next week's issue] on GitHub.
This way, I can include your stuff in here :D.

[next week's issue]: https://github.com/ReswitchedWeekly/ReswitchedWeekly.github.io/issues/30
[Discord]: https://discordapp.com/invite/DThbZ7z