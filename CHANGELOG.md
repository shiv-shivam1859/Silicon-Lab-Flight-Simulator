# Silicon-Lab-Flight-Simulator - My Development Log

I started this project in the summer of 2025 to teach myself complex aerodynamics, physics programming, and Three.js. This log tracks my progress, the physics bugs I've fought, and the features I've added.

# Silicon Lab Flight Simulator 🚀

### [2.1.0] - 06/05/2026 (Production Spec Exporter)
- Added a **"Spec Sheet (.txt)"** generator to the Export menu.
- Engineers can now instantly download a fully formatted Bill of Materials (BOM) containing precise airframe dimensions, material selections, and predicted flight parameters (Apogee, Max-Q, Mach) to share with production teams.

## Phase 6 — The Complete Package
### [2.0.0] - 16/04/2026 (AI Assistant, Transonic Aero & Pro UI)
- **MASSIVE REWRITE:** Graduated the visualizer into a professional aerospace suite. Split the UI into three dedicated workspaces: Engineering, AI Lab, and Simulation.
- **Generative AI Engine:** Integrated an LLM copilot that can holistically optimize rocket geometries, maximize apogee, and diagnose flight failure states.
- **Transonic Aerodynamics:** Upgraded the math engine to calculate dynamic skin friction (Reynolds numbers) and transonic drag spikes (Mach multipliers).
- **Structural Failure Simulation:** The physics engine now simulates catastrophic failure. If you exceed the Max-Q limit of your body tube material, or the Fin Flutter Velocity of your fin material, the rocket will shred mid-flight.
- **Interactive Telemetry:** Built a post-flight graph overlay to scrub through Altitude, Velocity, and Acceleration logs.
- **Smart Unit System:** Rebuilt the input system to allow on-the-fly conversions between Metric and Imperial units (cm, in, m, g, oz).
- **Advanced Recovery:** Implemented Dual-Deployment capabilities (Drogue at apogee, Main at specified altitude).
- **STL Engineering:** Added the ability to import custom 3D models and export multi-part `.zip` files for actual 3D printing.

## Phase 5 — Environment Engine
### [1.5.2] - 28/01/2026 (Physics Engine Sub-stepping)
- The Max-Q bug survived the last patch. Basic Euler integration simply cannot handle extreme dynamic pressure at high velocities. 
- RE-WROTE the physics loop to use **Sub-stepping**. The math engine now loops 10 separate times per visual frame, making the time-step incredibly small and the aerodynamics mathematically bulletproof. No more death spins.

### [1.5.1] - 25/01/2026 (Max-Q Stability Hotfix)
- Discovered a massive numerical instability bug. At Max-Q (peak velocity), the dynamic pressure was so high that my basic Euler integration couldn't handle the restorative torque, causing the rocket to overcorrect and death-spin.
- Patched the physics loop by clamping the maximum Angle of Attack, tightening the delta-time bounds, and adding a numerical dampener to the pitch rate.

### [1.5.0] - 10/01/2026 (Launch Pad & Atmosphere)
- Overhauled the 3D scene rendering. Replaced the basic grid with an infinite ground plane and atmospheric depth fog.
- Built a procedural metallic launch pad for the rocket to sit on.
- Upgraded the lighting system with hemispheric and directional lights to make the metallic reflections on the rocket and pad look significantly more realistic.

## Phase 4 — Recovery & Full Flight Profile
### [1.4.0] - 05/12/2025 (Parachute Deployment)
- Built an Apogee Detection algorithm into the physics loop (detects exactly when vertical velocity goes negative).
- Implemented a Recovery System UI with an adjustable Parachute Diameter.
- Programmed a secondary aerodynamic drag state. When the parachute deploys, the simulation dynamically swaps the reference area and drag coefficient to simulate terminal velocity descent.
- Added a 3D visual parachute that pops out at apogee!

## Phase 3 — Aerodynamics
### [1.3.1] - 14/11/2025 (The Damping Fix)
- FIXED THE TUMBLE BUG! I researched aerospace physics and discovered pitch damping derivatives ($C_{mq}$). 
- Implemented damping torque into the rotational physics loop. The rocket now stabilizes itself gracefully and weathercocks into the wind instead of spinning out of control.

### [1.3.0] - 26/10/2025 (Wind + Horizontal Motion)
- Upgraded the physics engine to 2D! Added horizontal velocity tracking ($V_x$) to simulate wind drift.
- Built a Crosswind slider in the UI.
- Calculated rotational inertia and torque based on the Barrowman Center of Pressure.

## Phase 2 — Simulation Core
### [1.2.1] - 05/10/2025 (Validation Layer)
- Added strict unit system enforcement and input sanity checks. 
- Upgraded the UI to allow direct number typing instead of just sliders.

### [1.2.0] - 18/09/2025 (The Propulsion Model)
- Replaced my dummy thrust values with a real commercial motor lookup table (using Estes & AeroTech specs).
- Wrote a 1D vertical kinematics integrator using the Euler method to simulate the flight profile.
- Built a Live Flight Telemetry HUD.

## Phase 1 — Core Engine
### [1.1.1] - 28/08/2025 (Geometry Bug Fix)
- Realized my $X_n$ math for conical shapes was wrong. Pushed a hotfix to correct the Barrowman equations so the COP marker accurately shifts when changing nose profiles.

### [1.1.0] - 12/08/2025 (Basic Stability)
- Spent the last few weeks learning aerodynamic algebra. Implemented the Barrowman equations for calculating the Center of Pressure (COP) and Center of Mass (COM).

### [1.0.0] - 20/07/2025 (Visual Foundation)
- Started the project! 
- Figured out how to use Three.js to generate dynamic 3D meshes (Body tubes, Nose cones, and Fins) using web inputs.