# ProjectionMappingApplesoftBasic

This program is a basic 3D Cube Simulation written in Applesoft Basic. You can try it yourself on "https://www.calormen.com/jsbasic/", or on any other emulator by uploading the "CubeSim.txt".
![WhatsApp Bild 2024-07-11 um 12 07 10_659c0f17](https://github.com/LukeBarthel/ProjectionMappingApplesoftBasic/assets/175216318/b0f5fe0a-06a6-4e90-8eba-58589af613a0)

## 1. Variable Initialization
In Applesoft Basic, only the first two letters of a variable are significant. To avoid confusion, short variable names are used:

- hgr: Initializes high-resolution graphics mode.
- cx, cy, sd: Cube position coordinates and side depth.
- xv, yv, zv: Cube movement velocities.
- dim c3(7,2): Defines a 3D array c3 to hold the 3D coordinates of the cube’s vertices.
- dim c2(7,1): Defines a 2D array c2 to hold the projected 2D coordinates of the cube’s vertices.
- cs: Cube size.
- f: Frame buffer toggle.
- rs: Rotation speed.
- buffer: Boundary buffer size to detect collisions.
- gosub 1000: Calls subroutine 1000 to initialize the cube’s vertices.

## 2. Main Loop
The main loop calls various subroutines to handle different aspects of the simulation:

Subroutines Called:
- Movement (gosub 4000): Updates the cube's position and applies rotation.
- Projection (gosub 2000): Converts 3D coordinates to 2D.
- Collision Detection (gosub 5000): Checks if the cube hits the screen borders and bounces it back if necessary.
- Drawing (gosub 3000): Renders the cube on the screen.
- Delay (gosub 7000): Adds a delay to control the simulation speed.
- Key Listener (gosub 8000): Handles keyboard input to control the cube.

## 3. Cube Initialization
Defines the 3D coordinates of the cube’s vertices based on its size and initial position:

Loop: Iterates over the 8 vertices of the cube and sets their coordinates.
## 4. Coordinate Projection
Converts 3D coordinates to 2D for display:

Projection Logic: Adjusts coordinates by reducing the Z-axis effect to project a 3D point onto a 2D plane.
## 5. Drawing the Cube
Draws the cube using the 2D projected coordinates:

Frame Buffer: Toggles between frame buffers to avoid flickering.
Line Drawing: Connects the vertices to form the cube's edges using hplot.
## 6. Cube Movement
Updates the cube's position based on velocity and applies rotation if enabled:

Position Update: Moves the cube by adding velocity to its current position.
Rotation Application: Calls the rotation subroutine to update the coordinates.
## 7. Collision Detection
Checks if the cube has hit the screen borders and reverses its direction if it has:

Boundary Check: Reverses velocity when a boundary is hit to make the cube bounce back.
## 8. Key Listener and Event Manager
Handles keyboard input for controlling the cube:

Key Press Detection:
- 'up' and 'down' Adjust movement speed
- 'r' toggles rotation
- 'f' and 's' modify rotation speed.
## 9. Rotation Matrices
Applies rotation to the cube around the X, Y, and Z axes:

Rotation Logic: Uses trigonometric functions to rotate the cube's vertices around the axes.
## 10. Delay Function
Creates a delay to control the simulation speed:

Loop Delay: Iterates over a loop to create a pause, simulating a delay.
