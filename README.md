# Project README

## Overview
The project is a simple C application that visualizes a sine wave using a graphical user interface. It supports various platforms and compilation methods, including Linux, Windows (via Wine), and WebAssembly.

## Features
- Visual representation of a sine wave.
- Cross-platform support for Linux, Windows, and WebAssembly.
- Compilation and execution through Makefiles tailored for each platform.

## Project Structure
```
<Project>/
├── build/              # .exe files produced by Main.c
├── libs/               # *.c for bin
├── src/                # source code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── Makefile.web        # Emscripten Build configuration
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - **Linux**: X11, PNG, JPEG
  - **Windows**: WINAPI, User32, GDI32, Winmm
  - **WebAssembly**: Emscripten

## Build & Run
### Linux
To build and run the application on Linux:
```sh
cd <Project>
make -f Makefile.linux all
make -f Makefile.linux exe
```

### Windows (via Wine)
To build and run the application on Windows using Wine:
```sh
cd <Project>
make -f Makefile.wine all
WINEPREFIX=~/wine64 WINEARCH=win64 wine ./build/Main.exe
```

### WebAssembly
To build and run the application in a web browser using WebAssembly:
```sh
cd <Project>
make -f Makefile.web all
make -f Makefile.web exe
# Open http://localhost:8080 in your browser
```

These instructions ensure that you can compile and execute the project on different platforms using the provided Makefiles.