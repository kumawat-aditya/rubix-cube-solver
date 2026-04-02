# Rubik's Cube Solver

[![C++](https://img.shields.io/badge/language-C%2B%2B17-blue.svg)](https://isocpp.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Algorithm: CFOP](https://img.shields.io/badge/algorithm-CFOP-green.svg)](docs/ARCHITECTURE.md)

A terminal-based Rubik's Cube solver written in C++17 that uses the **CFOP method** (Cross → F2L → OLL → PLL). The program accepts a scrambled cube state via interactive color-by-color input, solves it across all six possible orientations to find the shortest solution, then walks through each move step-by-step in full ANSI color in the terminal.

---

## Tech Stack

| Component        | Technology                                                          |
| ---------------- | ------------------------------------------------------------------- |
| Language         | C++17                                                               |
| Standard Library | STL (`vector`, `string`, `chrono`, `thread`, `algorithm`, `random`) |
| Output           | ANSI escape codes (no external GUI library)                         |
| Build            | `g++` direct compilation (GCC 15+)                                  |
| Algorithm        | CFOP — Cross, F2L, OLL, PLL                                         |

No third-party libraries or package managers are required.

---

## Prerequisites

- A C++17-capable compiler — GCC 9+ or Clang 9+ recommended
- A POSIX-compatible terminal with ANSI color support (Linux / macOS Terminal / Windows Terminal)

---

## Installation

**A. Download direct executable from the link:**
[DOWNLOAD](https://github.com/kumawat-aditya/rubix-cube-solver/releases/tag/v2.0.0)

OR

**B. Clone the repository:**

```bash
git clone https://github.com/kumawat-aditya/rubix-cube-solver.git
cd rubix-cube-solver
```

**Compile all source files:**

```bash
g++ -std=c++17 -O2 -o rubiks_cube_solver \
    rubixmain.cpp \
    Cube.cpp \
    Cross.cpp \
    F2l.cpp \
    Oll.cpp \
    Pll.cpp \
    CubeSolver.cpp \
    miscellaneous.cpp \
    Optimiser.cpp
```

**Run:**

```bash
./rubiks_cube_solver
```

> A pre-built Linux binary (`rubiks_cube_solver`) is also included in the repository root.

**video guid for the installation**

https://github.com/kumawat-aditya/rubix-cube-solver/assets/92208854/ad1c92ea-0dfa-43b7-aecd-30aacb12b60f

---

## How to Use

1. Launch the program. An ASCII banner is printed and the program displays the current cube state (initially blank/default).

2. You are prompted to enter the colors of each face one row at a time. Enter each color as a **single character**:

   | Character | Color  |
   | --------- | ------ |
   | `r`       | Red    |
   | `g`       | Green  |
   | `b`       | Blue   |
   | `y`       | Yellow |
   | `w`       | White  |
   | `o`       | Orange |

3. Faces are entered in this order: **Face → Right → Back → Left → Top → Bottom**. Top and Bottom have a special row/column ordering to match physical cube orientation — follow the on-screen prompts.

4. After all 54 stickers are entered, the solver validates color counts. If invalid, you are asked to retry.

5. The solver begins, printing a running count of attempted solutions. On completion it displays:
   - The best solution found (fewest total moves)
   - Move counts broken down by stage: Cross / F2L / OLL / PLL
   - Total solve time in milliseconds

6. Press `1` to animate the solution step-by-step (2-second delay between moves) or `0` to exit.

**Check this video tutorial to know how it works...**

https://github.com/kumawat-aditya/rubix-cube-solver/assets/92208854/d5439d2c-d5a7-4c32-bf5a-bc98b07f15c7

---

## Move Notation

The solution output uses standard Rubik's Cube notation:

| Notation          | Meaning                      |
| ----------------- | ---------------------------- |
| `F`               | Front face clockwise         |
| `FP`              | Front face counter-clockwise |
| `F2`              | Front face 180°              |
| `R` / `RP` / `R2` | Right face CW / CCW / 180°   |
| `B` / `BP` / `B2` | Back face CW / CCW / 180°    |
| `L` / `LP` / `L2` | Left face CW / CCW / 180°    |
| `U` / `UP` / `U2` | Upper face CW / CCW / 180°   |
| `D` / `DP` / `D2` | Down face CW / CCW / 180°    |
| `M` / `MP`        | Middle slice CW / CCW        |
| `E` / `EP`        | Equatorial slice CW / CCW    |
| `S` / `SP`        | Standing slice CW / CCW      |

---

## Project Structure

```
rubix-cube-solver/
├── rubixmain.cpp          # Entry point — wires CubeSolver, measures time, prints result
│
├── Cube.h / Cube.cpp      # Base class: cube state, all 18 face rotations, 6 whole-cube
│                          #   reorientations, color-validated input, terminal display
│
├── CubeSolver.h / .cpp    # Orchestrator: multi-start search over all 6 axes,
│                          #   holds best solution vectors, animated step printing
│
├── Cross.h / Cross.cpp    # Stage 1 — bottom-cross solver (inherits Cube)
├── F2l.h / F2l.cpp        # Stage 2 — first-two-layers solver (inherits Cube)
├── Oll.h / Oll.cpp        # Stage 3 — orientation of last layer (inherits Cube)
├── Pll.h / Pll.cpp        # Stage 4 — permutation of last layer (inherits Cube)
│
├── Optimiser.h / .cpp     # Static utility: collapses adjacent redundant moves
│
├── colors.h               # ANSI escape-code macros (foreground, background, style)
├── rotationAliases.h      # Preprocessor aliases mapping F/R/B/L/… to method calls
├── heading.h              # ASCII-art title rendering for the CLI splash screen
├── miscellaneous.h / .cpp # Terminal utilities: clearLines(), set_font_color(), ch_to_clr()
│
├── rubiks_cube_solver     # Pre-built Linux x86-64 binary
├── cube solver tutorial/  # Video walkthroughs (.mp4 / .GIF)
└── demo-screenshots/      # Demo video clip
```

---

## Quick Links

- [Architecture & Design](docs/ARCHITECTURE.md)
- [CFOP Method Reference](https://ruwix.com/the-rubiks-cube/cfop-fridrich-method/)

---

## Environment Variables

This project does not use environment variables or configuration files. All runtime behavior is controlled through interactive stdin prompts.

---

## Acknowledgments

Special thanks to the [RUWIX](https://ruwix.com/) community for their valuable insights and contributions to the C.F.O.P method. This program would not have been possible without the collective efforts of cubers worldwide.

---

## License

This Rubik's Cube Solver program is open-source and licensed under the MIT License. Feel free to modify and distribute it according to the terms of the license. Happy cubing!