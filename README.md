# Pointillism Flower (Sky Blue Edition) 🌸

A generative pointillist art experiment in Python that simulates the complete lifecycle of a blooming flower: sprouting from textured soil, opening in multi-layered sky-blue petals, emitting a glowing aura, and gradually wilting over time.

<img width="1425" height="705" alt="Sky blue pointillism flower" src="flower_blue.png" />

## Features
- **Procedural Pointillism:** Renders soil, stem, leaves, and petals using tens of thousands of dynamic point particles ("splats") rather than solid fills.
- **Sky-Blue Palette:** Four layered petal rings shade from deep blue at the outer edge to near-white at the center, with pale blue rims and highlights. The halo, orbital ring and sparkles are tinted to match.
- **Keyframe-Driven Lifecycle:** Smoothly interpolates through distinct phases: soil disturbance, stem elongation, leaf unfurling, full blossom, and gradual decay.
- **Bézier Curves & 3D Projections:** Uses parametric cubic Bézier curves for the stem and projects layered 3D petal geometry with depth sorting and wind sway.
- **Atmospheric FX & Aura:** Orbital energy rings, pulsing stamens, soft halos, and fluttering petals that detach and fall as the flower wilts.
- **Interactive GUI & Batch Exporters:** Tkinter window with keyboard controls, plus headless flags to export PNG stage frames or an animated GIF.

## Requirements

- Python 3.8+
- `numpy`
- `Pillow`
- `tkinter` (bundled with most Python installs; needed only for the interactive viewer)

```bash
pip install numpy pillow
```

## How to Run

```bash
# Run interactive desktop viewer
python flower_blue.py

# Export stage PNGs (flower_1.png ... flower_5.png) and flower_stages.png strip
python flower_blue.py --png

# Export animated GIF (flower.gif)
python flower_blue.py --gif
```

## Controls (interactive viewer)

| Key | Action |
|-----|--------|
| `Space` | Pause / resume |
| `R` | Restart the animation |
| `S` | Save the current frame as `flower_frame.png` |
| `Esc` | Quit |

## Configuration

Tweak these constants at the top of `flower_blue.py`:

| Constant | Purpose |
|----------|---------|
| `SEED` | Random seed; change it for a different flower |
| `TIME_SCALE` | Animation speed (higher = slower) |
| `TICK_MS` | Delay between frames in the viewer |
| `WIN_FRAC` | Window size as a fraction of screen height |
| `LOOP` | Set to `True` to replay automatically after the flower wilts |

To recolor the flower, edit `LAYERS` (petal palettes), `RIM_PAL` and `HI_PAL` (rims and highlights), and the glow colors inside `Plant.render`.
