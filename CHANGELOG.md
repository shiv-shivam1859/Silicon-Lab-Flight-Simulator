# Silicon-Lab-Flight-Simulator - My Development Log

I started this project in the summer of 2025 to teach myself complex aerodynamics, physics programming, and Three.js. This log tracks my progress, the physics bugs I've fought, and the features I've added.

## Phase 5 — Environment Engine
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
- *Bug Note:* Adding wind completely broke the physics engine. The rocket goes into a positive-feedback loop and death-spins (tumbles) uncontrollably every time it launches. Need to figure out why this is happening.

## Phase 2 — Simulation Core
### [1.2.1] - 05/10/2025 (Validation Layer)
- Added strict unit system enforcement and input sanity checks. 
- Upgraded the UI to allow direct number typing instead of just sliders.
- Built a Toast Notification system because I kept accidentally typing in negative values or confusing millimeters with centimeters, which was crashing the math engine with `NaN` errors.

### [1.2.0] - 18/09/2025 (The Propulsion Model)
- Replaced my dummy thrust values with a real commercial motor lookup table (using Estes & AeroTech specs).
- Wrote a 1D vertical kinematics integrator using the Euler method to simulate the flight profile.
- Added dynamic mass depletion (the rocket actually gets lighter in the simulation as the motor burns propellant over time).
- Built a Live Flight Telemetry HUD.

## Phase 1 — Core Engine
### [1.1.1] - 28/08/2025 (Geometry Bug Fix)
- Realized my $X_n$ math for conical shapes was wrong. Pushed a hotfix to correct the Barrowman equations so the COP marker accurately shifts when changing nose profiles.

### [1.1.0] - 12/08/2025 (Basic Stability)
- Spent the last few weeks learning aerodynamic algebra. Implemented the Barrowman equations for calculating the Center of Pressure (COP) and Center of Mass (COM).
- Added visual red and blue spherical markers to the 3D model to show exactly where the COM and COP are located.
- Built a live HUD to display the Static Stability Margin in calibers so I know if the rocket is safe to fly.

### [1.0.0] - 20/07/2025 (Visual Foundation)
- Started the project! 
- Figured out how to use Three.js to generate dynamic 3D meshes (Body tubes, Nose cones, and Fins) using web inputs.
- Built the initial user interface using Tailwind CSS and imported my custom logo.
- Got basic .STL exporting to work so I can actually 3D print the designs I make in the app!