# Rubik's Cube Solver v2.0.0 _(by aditya kumawat)_

`_solve any scramble in seconds_`

![Static Badge](https://img.shields.io/badge/C%2B%2B-language-blue)

## Introduction

Welcome to my Rubik's Cube Solver program! This C.F.O.P (Cross, F2L, OLL, PLL) based solver is designed to efficiently and quickly solve a Rubik's Cube within an astonishing 2 seconds. Whether you're a beginner or an experienced cuber, this program will showcase the power of the C.F.O.P method in solving the cube.

## Prerequisites

Before using the Rubik's Cube Solver, ensure you have the following:

- A working C++ compiler (e.g., G++) to compile the C++ program.
- A Rubik's Cube in a solvable state to test the solver.

## Installation

A. Download direct executable from the link:
[DOWNLOAD](https://github.com/kumawat-aditya/rubix-cube-solver/releases/tag/v2.0.0)

B. OR Clone the repository to your local machine or download the source code as a ZIP file.

```
 git clone https://github.com/kumawat-aditya/rubix-cube-solver.git
```

### video guid for the installation

https://github.com/kumawat-aditya/rubix-cube-solver/assets/92208854/ad1c92ea-0dfa-43b7-aecd-30aacb12b60f

## How to Use

1. Compile the rubiks_cube_solver.c file using your preferred C compiler:

```
 g++ -o rubiks_cube_solver rubixmain.cpp Cube.cpp Cross.cpp F2l.cpp Oll.cpp Pll.cpp CubeSolver.cpp miscellaneous.cpp Optimiser.cpp
```

2. Run the compiled executable:

```
./rubiks_cube_solver
```

3. Follow the on-screen instructions to provide the current cube configuration (scramble) in a user-friendly format. For example:

```
ENTER THE COLORS OF "FACE" SIDE OF THE CUBE:
    row_0-> b r g
    row_1-> g b o
    row_2-> y w b
    ...
```

4. Sit back and watch the magic happen! The solver will quickly analyze the configuration and display the optimal solution, along with the visualization of each step.

### Check this video tutorial to know how it works...

https://github.com/kumawat-aditya/rubix-cube-solver/assets/92208854/d5439d2c-d5a7-4c32-bf5a-bc98b07f15c7

## Notations

In order to effectively use the Rubik's Cube solver program, it's important to understand the notations used to describe the different moves and rotations of the cube. The following symbols represent the basic movements:

    F: Front face clockwise
    FP: Front face counterclockwise
    B: Back face clockwise
    BP: Back face counterclockwise
    U: Upper face clockwise
    UP: Upper face counterclockwise
    D: Down face clockwise
    DP: Down face counterclockwise
    L: Left face clockwise
    LP: Left face counterclockwise
    R: Right face clockwise
    RP: Right face counterclockwise

Each of these movements can be performed by appending an apostrophe to its symbol for the counterclockwise direction.
Example

To illustrate, let's say you want to rotate the front face clockwise and then the upper face counterclockwise. You would use the following sequence of notations:

    F - Rotate the front face clockwise.
    UP - Rotate the upper face counterclockwise.

These notations allow you to describe the steps needed to solve the Rubik's Cube using the solver program.

For a more comprehensive guide on Rubik's Cube notations and advanced techniques, you can refer to https://ruwix.com/the-rubiks-cube/notation/.

## Features

- Fast Solver: The program utilizes advanced algorithms and optimizations to achieve a blazingly fast solve time of just 2 seconds. It showcases the efficiency of the C.F.O.P method.
- Interactive Interface: The solver comes with an interactive command-line interface that guides you through the solving process. It displays step-by-step solutions and provides real-time feedback.
- Random Scramble: Test the solver's prowess by providing a random cube scramble. The program will quickly analyze the cube's configuration and output the optimal solution.
- Solution Visualization: The program visualizes the cube's movement for each step of the solution, allowing you to understand the solving process better.
- User-Friendly: Whether you're a beginner or an experienced cuber, the solver is designed to be user-friendly and intuitive.

## C.F.O.P Method

The C.F.O.P method (Cross, F2L, OLL, PLL) is a popular and widely used solving technique in the world of speedcubing. It involves four main steps:

- Cross: Create a cross on one side of the cube, usually starting with the white face.
- F2L (First Two Layers): Solve the first two layers of the cube simultaneously by pairing corner-edge pieces.
- OLL (Orientation of Last Layer): Orient the last layer so that all the pieces have the correct color on the top face.
- PLL (Permutation of Last Layer): Permute the last layer's pieces to fully solve the cube.

## Acknowledgments

Special thanks to the [RUWIX](https://ruwix.com/) community for their valuable insights and contributions to the C.F.O.P method. This program would not have been possible without the collective efforts of cubers worldwide.

## Contact

If you have any questions, suggestions, or encounter any issues with the program, feel free to contact me at kumawataditya105@gmail.com.

## License

This Rubik's Cube Solver program is open-source and licensed under the MIT License. Feel free to modify and distribute it according to the terms of the license. Happy cubing!
