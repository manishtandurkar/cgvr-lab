# CGVR Lab Programs

OpenGL / GLUT programs for the Computer Graphics and Visualization (CGVR) lab.

## Common header (Linux)

Put this at the top of any program. It works for all 12 programs:

```cpp
#include <iostream>
#include <cmath>
#include <algorithm>
#include <GL/glut.h>
using namespace std;
```

- `iostream`: `cin` / `cout` for keyboard input
- `cmath`: `sin`, `cos`, `sqrt`, `abs` (rotation, circle, sphere, cylinder)
- `algorithm`: `min`, `max`, `swap` (scan-line fill, clipping)
- `GL/glut.h`: GLUT, which also pulls in `GL/gl.h` and `GL/glu.h` (`gluOrtho2D`, `gluPerspective`, etc.)

## Setup (Ubuntu / Debian)

Install the compiler and the OpenGL / GLUT libraries once:

```bash
sudo apt update
sudo apt install g++ freeglut3-dev
```

On Fedora: `sudo dnf install gcc-c++ freeglut-devel`

## Compile and run

```bash
g++ 1_bresenham_line.cpp -o bresenham_line -lGL -lGLU -lglut
./bresenham_line
```

Use the same pattern for every program, changing only the file name:

```bash
g++ <file>.cpp -o <name> -lGL -lGLU -lglut
./<name>
```

To compile all of them at once:

```bash
for f in [0-9]*.cpp; do g++ "$f" -o "${f%.cpp}" -lGL -lGLU -lglut; done
```

Note: `all.cpp` contains every program together (12 `main()` functions), so it is for reference only and will not compile as one file.

## Programs and their inputs

| # | File | Input |
|---|------|-------|
| 1 | `1_bresenham_line.cpp` | Choose 1 (keyboard) or 2 (mouse). Keyboard: number of lines, then `x1 y1 x2 y2` for each. Mouse: click two points per line. |
| 2 | `2_bresenham_circle.cpp` | Choose 1 (keyboard) or 2 (mouse). Keyboard: `xc`, `yc`, `r`. Mouse: click the centre, then a point on the circle. |
| 3 | `3_rectangle_spin.cpp` | None (animation) |
| 4 | `4_cylinder_parallelepiped.cpp` | None |
| 5 | `5_sierpinski_gasket.cpp` | Number of subdivisions (e.g. `3`). |
| 6 | `6_sphere.cpp` | None |
| 7 | `7_scanline_areafill.cpp` | Number of sides, then `x y` for each vertex (e.g. 4 sides: `100 100  400 150  350 400  150 350`). |
| 8 | `8_cohen_sutherland_line.cpp` | None |
| 9 | `9_liang_barsky_line.cpp` | None |
| 10 | `10_sutherland_hodgeman_polygon.cpp` | None |
| 11 | `11_house_rotate_reflect.cpp` | Choose 1 (rotation): enter `t xr yr` (angle in degrees, pivot point). Choose 2 (reflection): enter `m c` (line y = mx + c). |
| 12 | `12_color_cube_spin.cpp` | None (animation) |

Close the output window to exit the program.
