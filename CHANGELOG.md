# Silicon Lab - My Development Log

I started this project in the summer of 2025 to teach myself complex aerodynamics, physics programming, and Three.js. This log tracks my progress, the physics bugs I've fought, and the features I've added.

## Phase 1 — Core Engine
### [1.1.0] - 12/08/2025 (Basic Stability)
- Spent the last few weeks learning aerodynamic algebra. Implemented the Barrowman equations for calculating the Center of Pressure (COP) and Center of Mass (COM).
- Added visual red and blue spherical markers to the 3D model to show exactly where the COM and COP are located.
- Built a live HUD to display the Static Stability Margin in calibers so I know if the rocket is safe to fly.

### [1.0.0] - 20/07/2025 (Visual Foundation)
- Started the project! 
- Figured out how to use Three.js to generate dynamic 3D meshes (Body tubes, Nose cones, and Fins) using web inputs.
- Built the initial user interface using Tailwind CSS and imported my custom logo.
- Got basic .STL exporting to work so I can actually 3D print the designs I make in the app!