# HackerBox-0036
Created alittle physics toy out of [HackerBox 0036](https://www.instructables.com/id/HackerBox-0036-JumboTron/). It's using a very basic [Verlet Integration](https://en.wikipedia.org/wiki/Verlet_integration) and only includes functionality for bouncing particles off walls and eachother at the moment. I would like to add more functionality from my [full Verlet Project](https://github.com/jgoergen/VerletAlgorythm) eventually. This will serve as a good way to experiment with pumping more speed out of a simple c version of the code. 

Ofcourse, this assumes you're using the same hardware setup in basically the same way **with one imortant difference**!
The "Lat" pin definition for the display has been changed from 22 to 4. I wanted to eventually add some I2C functionality ( a gyroscope among other things ) so I needed this pin open.

Again **LAT Pin 22 is now Pin 4 on the ESP32!!!**

Once uploaded the joystick works as follows:
"K1" clears all particles from the scene.
"K2" adds one particle at a time.
"K3" regenerates the 'scene' with between 200 and 400 particles, this also randomizes the friction of the 'ground' as well.
"K4" removes on particle at a time.
"Joystick" tilts "the surface" which imparts gravity on the balls and makes them move.

Things that could be improved:
1) Look into replacing the square rooting with approximations
2) Push the physics code onto a seperate thread
3) Bust the code up into seperate files (main, display, input, etc.)
4) Convert the Verlet code into a library, pull the display code out of it
5) Add constraints with pinning
6) Add constraint & paricle collision
7) Add constraint & constraint collision