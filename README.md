# Body Form Maker (`body-form-maker.html`)

An interactive, standalone 3D studio for designing custom-fitted **female** dress forms and body mannequins, with real-time tape-measure circumference tracking, measurement locking, anatomical sculpting, and watertight `.STL` / `.OBJ` export for 3D printing or digital draping.

> **Current Scope Notice:** This tool currently supports **female body forms only**. It is built around female anatomical topology and morph targets—including cup/band sizing, teardrop vs. spherical breast distribution, underbust crease definition, and the lower-abdominal / uterine curve near the pelvis.

---

## Features

- **100% Standalone Single-File App (`body-form-maker.html`)**
  - Runs directly in any modern browser (Chrome, Safari, Firefox, Edge) on Mac, Windows, or Linux.
  - Requires **no server, no installation, and no internet connection**—simply download and double-click `body-form-maker.html`.
- **Exact Measurements + Lock Solver (`in` or `cm`)**
  - Type exact tape-measure circumferences for **Full Bust**, **Underbust (Band)**, **Natural Waist**, **High Hip (Pelvic Shelf)**, **Low Hip / Full Seat**, **Neck Base**, and **Left/Right Mid-Thigh**.
  - Press `Enter` to solve the 3D mesh to your exact measurement and **Lock** it fixed while you adjust shape sliders.
- **Anatomical Sculpting (30+ Morph Sliders)**
  - **Chest & Bust Geometry:** Separate controls for *Upper vs. Lower Pole Fullness* (`Teardrop` vs. `Spherical`), *Gravity / Ptosis & Underbust Crease*, *Side-Set Separation*, *Lateral Splay*, *Root Width*, and *Projection*.
  - **Waist & Pelvic Anatomy:** Dedicated *Uterine / Lower Belly Curve (Near Pelvis)* slider, *Front vs. Back Waist Distribution*, *Waist Side Taper vs. Front/Back Depth*, *High-Hip / Iliac Crest Shelf*, *Hip Dip (Trochanteric Depression)*, and *Lumbar Lordosis*.
  - **Left / Right Asymmetry:** Independent L/R cup size, shoulder drop, shoulder forward roll, pelvic tilt/hip hike, and spine lateral curve.
- **Privacy-Friendly Sharing**
  - Starts on a neutral **Standard Base** profile with generic creative archetypes (*Standard Base*, *Full Bust Teardrop*, *Hourglass*, *Petite*).
  - Clicking **Save Profile** saves your personal measurements strictly inside your own browser's `localStorage`—sharing the `.html` file never shares your personal measurements.
- **Watertight 3D Print Export (`.STL` & `.OBJ`)**
  - Exports manifold, watertight meshes in millimeters (`Z-Up` for `.STL`) with optional Catmull-Clark smoothing and a flat standing base at `1:1`, `1:2`, `1:4`, `1:6`, or `1:10` scale.

---

## Quick Start

1. Clone or download this repository:
   ```bash
   git clone https://github.com/ssmostagh/body-form-maker.git
   ```
2. Double-click **`body-form-maker.html`** to open it in your browser.
3. Enter your measurements in the left panel (in **inches** or **cm**) or select a starting archetype, customize the shape sliders on the right, and click **Download .STL (3D Print)** or **.OBJ**.
