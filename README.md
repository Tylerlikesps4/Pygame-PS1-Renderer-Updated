# Pygame PS1 Renderer

A lightweight software rasterizer inspired by the low-poly, low-resolution aesthetic of early PlayStation-era 3D graphics. This project renders textured triangle meshes using Python, Pygame, NumPy, and Numba, with a simple first-person camera and depth-buffered rasterization.

![Demo render](./demo.png)

## Features

- 3D mesh rendering from OBJ files
- Texture mapping with UV coordinates
- Depth-buffered triangle rasterization
- Camera movement and mouse-look controls
- Custom projection and transform pipeline
- No OpenGL dependency: rendering is performed in software

## Requirements

Install the Python dependencies:

```bash
pip install pygame numpy numba trimesh
```

## Run the Demo

Run from the repository root:

```bash
python main.py
```

The demo loads the bundled `demo.obj` model and `demo.png` texture.

## Controls

- `W` / `A` / `S` / `D` — move
- Mouse — look around
- `Space` — move up
- `Left Shift` — move down
- `Esc` — quit

## Project Structure

```text
.
├── camera.py        # First-person camera controls
├── main.py          # Pygame window and render loop
├── rasterize.py     # Textured triangle rasterizer
├── transform.py     # Model, camera, and projection transforms
├── util.py          # OBJ and texture loading utilities
├── demo.obj         # Sample mesh
├── demo.png         # Sample texture
└── README.md
```

## Rendering Overview

The renderer loads an OBJ mesh and its UV coordinates, transforms the mesh into camera space, and projects its vertices onto a 2D framebuffer. Each visible triangle is rasterized with texture sampling and a depth buffer. Numba is used to compile the rasterizer for faster execution.

## License

This repository does not currently include a license file. Check with the original project owner before redistributing or using the code beyond the permissions granted by GitHub's fork terms.

This repository is a fork of [BrentonCodes/Pygame-PS1-Renderer](https://github.com/BrentonCodes/Pygame-PS1-Renderer).
