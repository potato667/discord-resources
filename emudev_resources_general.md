# General Resources

- **Overview of emulation development: <https://stackoverflow.com/a/448689>**
- **Architecture overview of various consoles: <https://copetti.org/projects/consoles>**
- An introduction: <http://emulator101.com>
- Docs for various systems: <https://github.com/shonumi/Emu-Docs> (combine with resources below)
- Emulation blogs: <https://dolphin-emu.org/blog>, [[archived] byuu.net/](https://web.archive.org/web/20201221154920/https://byuu.net/), <http://emudev.de>, [[archived] noxa.org/emulation/](https://web.archive.org/web/20220928023912/http://www.noxa.org/blog/category/coding/emulation/), <http://melonds.kuribo64.net/>, <https://pcsx2.net/blog/tags/devblog>, <https://shonumi.github.io/articles.html>, etc
- Subreddit: <https://www.reddit.com/r/EmuDev>
- Building a computer from scratch: <https://www.nand2tetris.org>
- Books (not necessary): 
    - [[archived] noxa.org/emulation-books/](https://web.archive.org/web/20221014042726/http://www.noxa.org/blog/2011/08/21/emulation-books/)
    - <http://www.codeslinger.co.uk/files/emu.pdf>
- Write & run 8-bit code in the browser: <https://8bitworkshop.com>
- Our website: <https://emudev.org/> (in construction)

Most people start with a CHIP-8 emulator. As with any system, see <#482208284032499713> to get started.
*Note*: A great guide that still keeps it challenging is <https://tobiasvl.github.io/blog/write-a-chip-8-emulator/>.

After that, you can pretty much move to whatever system you want to. You don't _have_ to "work your way up" to it as many seem to think (relevant opinionated thread here: <https://goo.gl/CAvrd4>).
Just make sure you have the basics down first, study the source code of existing emulators (super important) and if you get stuck, ask questions here or in the subreddit.
If you contribute to a project that has its own community/resources, you should probably prioritize that.

## Emulation Terms
Explanations for some terms you might come across.
(for more info, look at source code of existing emulators, or ask others)

### HLE vs LLE
High Level Emulation vs Low Level Emulation
- <https://alexaltea.github.io/blog/posts/2018-04-18-lle-vs-hle>
- <http://emulation.gametechwiki.com/index.php/High/Low_level_emulation>

### CPU emulation, cached interpeters
- Code Translation Techniques: [[archived] noxa.org/building-an-xbox-360-emulator-part-6-code-translation-techniques/](http://www.noxa.org/blog/2011/08/21/building-an-xbox-360-emulator-part-6-code-translation-techniques/)
- Writing a Cached Interpreter: <https://emudev.org/2021/01/31/cached-interpreter.html>
- Faster interpreters: <http://www.emulators.com/docs/nx25_nostradamus.htm>
- Computed goto: https://eli.thegreenplace.net/2012/07/12/computed-goto-for-efficient-dispatch-tables

### Dynarecs/JITs and AOTs
Just-In-Time and Ahead-of-Time compilers.
- Wikipedia: <https://www.wikiwand.com/en/Just-in-time_compilation>  (just for an overview of what it is)
- <https://github.com/spencertipping/jit-tutorial>
- <http://blog.reverberate.org/2012/12/hello-jit-world-joy-of-simple-jits.html>
- <https://emudev.org/docs/1964-recompiling-engine-documentation.pdf>
- <https://bheisler.github.io/post/experiments-in-nes-jit-compilation>
- <https://andrewkelley.me/post/jamulator.html> (**AOT**. most other links here are about **JIT**ing)
- <https://www.davidsharp.com/tarmac/> (see pdf at the end)

### fastmem
Fast memory accesses using host MMU.
- <https://wheremyfoodat.github.io/software-fastmem>
- <https://dolphin-emu.org/blog/2016/09/06/booting-the-final-gc-game> (mentioned in "Theory 3")
- Faster interpreters: <https://www.alchemistowl.org/pocorgtfo/pocorgtfo06.pdf> (Section 3.4)
- <http://man7.org/linux/man-pages/man2/mprotect.2.html> (Unix API)
- <https://docs.microsoft.com/en-us/windows/win32/api/memoryapi/nf-memoryapi-virtualprotect> (Windows API)

### Software Rasterization
For emulating 3D systems.
- <https://fgiesen.wordpress.com/2013/02/17/optimizing-sw-occlusion-culling-index>

### Audio
- <https://nicolasallemand.com/2019/12/12/let-there-be-sound>
- <https://redream.io/posts/improving-audio-video-synchronization-multi-sync>

### FPGAs
- <https://zipcpu.com>
- <https://www.walknsqualk.com/post/014-tiny-fpga-bx>
- [Short introduction on writing HDLs, with Verilog puzzles you can solve online](https://hdlbits.01xz.net/wiki/Main_Page)

### Integrated Circuits
- <https://www.icreversing.com/chips> (IC library)

### Save States
- [Adding Save States to an Emulator](https://www.gregorygaines.com/blog/adding-save-states-to-an-emulator/)

### Emulator Update Loop
- [Emulator Polling vs. Scheduler Game Loop](https://www.gregorygaines.com/blog/emulator-polling-vs-scheduler-game-loop/)

## Useful libraries
- Multimedia libraries (For Audio/Video output, keyboard/controller input, etc)
  - [SDL2](https://www.libsdl.org/): C library for graphics, audio, input, threading, and more. Has bindings for several languages
  - [SFML](https://www.sfml-dev.org/): C++ library for video and input. Mostly aimed at gamedevs, but can be used for emudev too. Audio API generally considered unfit for emudev.
  - [Miniaudio](https://github.com/mackron/miniaudio): Single-header C audio library, supports all major desktop OSs + Android/iOS.

- UI frameworks:
  - [Qt](https://www.qt.io/): C++ GUI framework with bindings in several languages.
  - [Dear ImGui](https://github.com/ocornut/imgui): Immediate-mode GUI framework, focusing on ease-of-use
    - [ImGui Club](https://github.com/ocornut/imgui_club): Collection of useful ImGui widgets, including a memory editor
  - [Avalonia](https://github.com/AvaloniaUI/Avalonia): Portable .NET GUI framework
  - [GTK](https://www.gtk.org/)
  - [Nuklear](https://github.com/Immediate-Mode-UI/Nuklear): Single header C immediate mode GUI library
  - [WxWidgets](https://www.wxwidgets.org/)
  - [Gum](http://gumui.net/): A very versatile GUI framework that offers a lot of features and has a great community.

- Runtime code generation (emitter) libraries for use in JITs and assemblers:
  - [Xbyak](https://github.com/herumi/xbyak): Single header C++ x86-32 and x86-64 emitter
  - [Oaknut](https://github.com/merryhime/oaknut): Single header C++ arm64 emitter
  - [Dynasm](https://github.com/Esvandiary/DynASM): x86-32/x86-64/arm32/arm64/PowerPC/MIPS emitter written in C
  - [Luma](https://github.com/wheremyfoodat/Luma): Single header C++ 32-bit PowerPC emitter, with support for the Paired Singles ISA in the Gamecube/Wii/Wii U CPUs
  - [Vixl](https://github.com/Linaro/vixl): C++ arm32 and arm64 emitter for x86-32, x86-64 and arm64.
  - [asmjit](https://asmjit.com/): C++ emitter 
  - [Dynasm-rs](https://github.com/CensoredUsername/dynasm-rs): A dynasm-like library for Rust, using proc-macros

- Libraries for handling configuration files, game databases, etc:
  - [nlohmann/json](https://github.com/nlohmann/json): JSON for modern C++
  - [toml11](https://github.com/ToruNiina/toml11): TOML for modern C++
  - [mINI](https://github.com/metayeti/mINI): Single header C++ library for manipulating INI files

- Cryptography libraries for systems with crypto hardware:
  - [cryptopp](https://github.com/weidai11/cryptopp)
  - [OpenSSL](https://www.openssl.org/)

- [elfio](https://github.com/serge1/ELFIO): C++ library for reading and creating ELF files, useful for emulators that need to load ELFs or create ELFs for debugging purposes.
- [Capstone](https://github.com/capstone-engine/capstone): C disassembler library with support for too many architectures to enumerate
- [Keystone](https://github.com/keystone-engine/keystone): C assembler framework
- [glm](https://github.com/g-truc/glm): C++ library for faciliating vector, matrix and quaternion math. Particularly useful for graphics emulation.
- [Hips](https://github.com/wheremyfoodat/Hips): Single header C++ library for applying IPS, BPS and UPS patches
- [Discord-RPC](https://github.com/discord/discord-rpc): C++ library for adding discord RPC to your emulator, because we all love free advertisements.

---

## Reverse Engineering
In emulation, RE-ing is often needed for system BIOSes, operating systems, drivers, OS modules and games to aid in understanding of what the hardware does & emulate it properly when the documentation is insufficient or incomplete (ie. always).
It's a huge area of expertise & there is no be-all end-all resource, but a decent starting point might be <https://beginners.re> (older but free mirror: <https://mirrors.ocf.berkeley.edu/parrot/misc/openbooks/programming/ReverseEngineeringForBeginners.en.pdf>)
- These videos from LiveOverflow & stacksmashing are a fun introduction to some fundamental concepts: <https://www.youtube.com/playlist?list=PLniOzp3l9V82onKsktyyKlIenAAUj45Mk>
- There are _way_ too many resources about this. It's a skill used in many disciplines. Look around, find what you like (otherwise you might not be motivated for long).

### Static analysis
The industry standard tools are:
- **[Ghidra](https://ghidra-sre.org)**: There are loaders/extensions for pretty much all consoles/processors, search for them.
- **[IDA Pro](https://www.hex-rays.com/ida-pro)**: Proprietary, paid, closed-source. Industry-standard for professionals - especially before Ghidra it was the only viable option. I don't personally recommend it, especially for architectures other than x86. Also if you want to get it legally, it costs multiple thousands of dollars vs. Ghidra being free & open source.

### Dynamic analysis / Debugging
The standard tool that's cross-platform and supports many architectures is **gdb**.
- Many emulators implement "gdbstub"s that allow them to use a gdb client to debug guest code just like you would debug something running on the host. Meaning, you would be able to place breakpoints, step, etc via any gdb interface (ie. gdbgui), on GameBoy code or whatever you're emulating.
    - IDA Pro has debugging support that works with gdbstubs.
    - <https://hugsy.github.io/gef/>
    - <https://www.gdbgui.com>
- Other projects choose to make their own integrated debuggers with (ie. <https://github.com/ocornut/imgui>). This is perhaps more work, but more flexible (and many people don't like gdb).
    - For x86, the industry standard tool is <https://github.com/x64dbg/x64dbg>.
    - Frida: <https://frida.re>
    - <http://reddit.com/r/ReverseEngineering> and <http://reddit.com/r/REGames>

---

**Contributing**

Have something to add to this list? Submit a pull request [here](https://github.com/emudev-org/discord-resources/blob/main/emudev_resources_general.md).


**Note: If you're new here, scroll up to the top!**
