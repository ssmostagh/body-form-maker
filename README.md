# Body Form Maker (`body-form-maker.html`)

An interactive, standalone 3D studio for designing custom-fitted **female, male, and blended/androgynous** dress forms and body mannequins, with real-time tape-measure circumference tracking, measurement locking, anatomical sculpting, and watertight `.STL` / `.OBJ` export for 3D printing or digital draping.

---

## Features

- **100% Standalone Single-File App (`body-form-maker.html`)**
  - Runs directly in any modern browser (Chrome, Safari, Firefox, Edge) on Mac, Windows, or Linux.
  - Requires **no server, no installation, and no internet connection**—simply download and double-click `body-form-maker.html`.
- **Dual Anatomy Modes (`Female Form` | `Male Form`) + Continuous Blend**
  - Switch between **Female Form** and **Male Form** in the top header, or use the continuous **Base Anatomy Blend (`0% Female ↔ 100% Male`)** slider under *Proportions* to dial in custom androgynous or transitional body forms.
  - **Female Mode:** Quick **Bra Band & Cup** sizing (`28–56` band, `AA–N` cup), independent *Teardrop vs. Spherical* pole fullness, *Gravity / Underbust Crease*, *Side-Set Separation*, and *Uterine / Lower Belly Curve (Near Pelvis)*.
  - **Male Mode:** Quick **Suit / Chest & Waist Drop** sizing (`34" XS` to `60" 6XL`, `-8" Athletic` to `+4" Plus Waist` drop), dedicated **Pectoral Muscle Definition & Shelf**, **Upper Back / Latissimus Dorsi Width**, and upper-chest circumference solving.
- **Exact Measurements + Lock Solver (`in` or `cm`)**
  - Type exact tape-measure circumferences for **Full Bust / Full Chest**, **Underbust / Under-Chest**, **Natural Waist**, **High Hip (Pelvic Shelf)**, **Low Hip / Full Seat**, **HPS to Bust/Chest Line**, **Apex Span**, and **Mid-Thigh** (supporting petite through 6XL+ plus-size measurements).
  - Press `Enter` to solve the 3D mesh to your exact measurement and **Lock** it fixed while you adjust shape sliders.
- **Anatomical Sculpting (30+ Morph Sliders)**
  - **Chest & Bust / Pectoral Geometry:** Separate controls for *Upper vs. Lower Pole Fullness* (`Teardrop` vs. `Spherical`), *Gravity / Ptosis & Underbust Crease*, *Pectoral Muscle Definition*, *Upper Back / Lat Width*, *Side-Set Separation*, *Lateral Splay*, and *Projection*.
  - **Waist & Pelvic Anatomy:** Dedicated *Lower Belly / Uterine & Soft Apron Curve* slider, *Front vs. Back Waist Distribution*, *Waist Side Taper vs. Front/Back Depth*, *High-Hip / Iliac Crest Shelf*, *Hip Dip (Trochanteric Depression)*, and *Lumbar Lordosis*.
  - **Left / Right Asymmetry:** Independent L/R chest/cup volume, shoulder drop, shoulder forward roll, pelvic tilt/hip hike, and spine lateral curve.
- **Privacy-Friendly Sharing**
  - Starts on neutral **Standard Base** profiles with generic creative archetypes (*Standard Base*, *Full Bust Teardrop*, *Hourglass*, *Plus 2XL*, *Full 4XL*, *Petite* in Female Mode; *Standard 40R*, *Athletic V-Taper*, *Slim 38S*, *Broad 44R*, *Plus 2XL (48R)*, *Full 4XL (54R)* in Male Mode).
  - Clicking **Save Profile** saves your personal measurements strictly inside your own browser's `localStorage`—sharing the `.html` file never shares your personal measurements.
- **Watertight 3D Print Export (`.STL`, Sliced Multi-Part `.ZIP`, & `.OBJ`)**
  - **Single-File Export:** Exports manifold, watertight meshes in millimeters (`Z-Up` for `.STL`) with optional Catmull-Clark smoothing and a flat standing base at `1:1`, `1:2`, `1:4`, `1:6`, or `1:10` scale.
  - **Domestic 3D Printer Bed Slicer (`Slice for Printer`):** Automatically slices life-size (`1:1`) or half-scale (`1:2`) dress forms into numbered, flat-bottomed watertight blocks that fit standard home 3D printer build volumes (`220×220×250 mm` Ender/Prusa, `256×256×256 mm` Bambu Lab X1/P1/A1, `180×180×180 mm` Mini, or `300×300×300 mm`), complete with **9.6 mm alignment dowel pins and 10.2 mm mating sockets** (`0.30 mm` clearance) and a bundled `ASSEMBLY_GUIDE.txt`.

---

## Size Inclusivity & MakeHuman Dataset Limitations (Work in Progress)

Size inclusivity is an active priority for **Body Form Maker**, and I am actively working to improve how the 3D mesh models plus-size and larger bodies (`2XL`–`6XL+`).

Because this tool is built on top of the open-source **MakeHuman** base mesh and morph target dataset, it is currently constrained by the limits and biases of their underlying data:

1. **Constrained by the MakeHuman Dataset & Sampling Bias:**
   - Like most publicly available 3D anthropometric datasets, MakeHuman's base topology and linear morph targets reflect significant **data collection and sampling bias**—historically over-representing smaller, thinner body types while severely under-sampling larger and plus-size bodies.
   - Because I am currently limited by their dataset, extrapolating those linear vertex morphs to larger measurements can struggle to capture natural plus-size proportions and can produce overly smoothed or distorted contours if pushed too far on a single slider.
   - I have added custom composite torso/hip morph blending and plus-size starting archetypes (**Plus 2XL** and **Full 4XL**) to help bridge that gap right now, and I hope to keep improving this over time as I look for and incorporate more representative 3D body scan data.
2. **Tips for Getting the Best Fit Right Now (`2XL`–`6XL+`):**
   - **Start from `Plus 2XL` or `Full 4XL` (or raise `Body Mass / Soft Tissue` first):** If you type a `48"`–`60"+` waist or hip measurement directly onto MakeHuman's default base mesh without increasing overall body mass, the solver has to stretch individual ring morphs far past where MakeHuman's dataset was designed to go, which can cause pinching or ridges between the waist and hips. Starting from the **`Plus 2XL`** or **`Full 4XL`** archetype (or raising **Body Mass / Soft Tissue** under *Proportions* to `+120%`–`+220%`) expands the whole torso first so individual circumference locks stay smooth.
   - **Dial in Front/Back vs. Side Proportions with the Camera Views:** Because a single tape-measure circumference only tells the solver the total perimeter at a given height (`Y`)—and not how that fullness is distributed between the front, back, and sides—check the **3/4 View** and **Left/Right** profile cameras while your measurements are locked, and use **Lower Belly Curve**, **High-Hip Shelf**, **Hip Width (X)**, and **Hip Depth (Z)** to match your actual silhouette.

---

## Quick Start

1. Clone or download this repository:
   ```bash
   git clone https://github.com/ssmostagh/body-form-maker.git
   ```
2. Double-click **`body-form-maker.html`** to open it in your browser.
3. Choose **Female Form** or **Male Form** in the top header, enter your measurements in the left panel (in **inches** or **cm**) or select a starting archetype, customize the shape sliders on the right, and click **Download Single .STL**, **Slice for Printer (.ZIP / STLs)**, or **.OBJ**.
