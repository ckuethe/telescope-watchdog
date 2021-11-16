# telescope-watchdog
IMU-based watchdog to prevent your robotic telescope from going way out of bounds

For reasons I do not yet understand, my telescope mount sometimes gets very confused, flips over,
spins the wrong way, causes collisions between the OTA and the pier, or gets tangled up in its own
cabling. Luckily no damage has occured (so far) but I've had quite enough of that nonsense.

A 3DOF accelerometer would be sufficient to watch for unsafe elevation changes (my primary concern);
these days 6DOF IMUs (accelerometer+gyro) are cheap as chips and a 9DOF IMU with magnetometers can
be had for the same price as an IR/UV filter.

As my mount has both internal wifi and can be controlled via INDI/INDIGO, I have written a small
daemon to read an IMU and send a movement abort command if the position exceeds allowable limits.
