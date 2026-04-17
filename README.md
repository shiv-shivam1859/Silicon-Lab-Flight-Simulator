Silicon Lab Flight Simulator 🚀

A web-native 6-DOF aerospace simulation engine and parametric rocket design suite.

Silicon Lab Flight Simulator is an advanced aerospace engineering platform designed to bridge theoretical physics and practical rocket design. It goes beyond basic 3D visualization by implementing real aerodynamic models, numerical solvers, and AI-assisted engineering workflows to simulate realistic flight behavior and structural constraints.

⚠️ Important Notice

This project was initiated prior to being published on GitHub. Development progress was documented independently, and some commits may have modified timestamps to reflect the original timeline.

Core Engineering Capabilities
🚀 Flight Physics & Aerodynamics
Implements a 6-DOF physics model with a custom sub-stepped Euler integrator for numerical stability under high dynamic pressure (Max-Q).
Computes Barrowman stability parameters, including Center of Pressure (CP) and aerodynamic coefficients.
Models Reynolds-dependent skin friction and transonic drag rise using Mach-based correction factors.
🧠 AI Engineering Co-Pilot
Integrated LLM-driven assistant embedded into the design workflow.
Capable of:
Optimizing airframe geometry for target apogee
Maintaining static stability margins
Diagnosing aerodynamic and structural failure modes
🧱 Structural Integrity Simulation
Real-time monitoring of material limits under flight conditions
Detects and simulates:
Failure due to exceeding dynamic pressure (Max-Q)
Fin flutter based on material and velocity constraints
📊 Telemetry & Post-Flight Analysis
Live flight HUD displaying key parameters
Generates post-flight datasets and graphs for:
Altitude
Velocity
Acceleration
🪂 Recovery System Simulation
Supports dual-deployment recovery systems:
Drogue parachute at apogee
Main parachute at configurable altitude
Includes crosswind drift and descent modeling
🧩 CAD & Rapid Prototyping
Import custom .stl geometries
Export parameterized rocket designs as multi-part .zip packages ready for 3D printing

As a result, the commit history may appear non-linear. This does not affect the authenticity or continuity of development.