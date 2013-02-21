Well, finally here it is: The new firmware with the improved self level
Now it snaps to level like a champ!

Changes in FW:

1: Airplane functions removed: Airplane presets and "arming always on". The FW can still do airplane stabilization, but I recommend using OpenAero2 for that.

2: Widened the limits of the RX input signal for those who insist on using 150% servo travel with 150% dual rate. Tip: use the stick scaling in KK2 instead. Also notice that using such high servo travel may confuse the CPPM decoder, so always check in the RX monitor with all sticks and switches set to maximum PPM value. This applies only to CPPM users.

2: Set servo filter default to 50%.

3: Fixed the swapped labels in the CPPM setup screen.

When flashed with new FW, the KK2 will do a factory reset. Do not forget to check the layout and other settings, and calibrate the accelerometers.


Changes in usage:

1: For well performing self-level the gyros must have a good calibration. Large changes in temperature may upset the self-level. Therefore the KK2 does a gyro calibration each time it is armed. At that time it must be kept completely still, i. e. standing on the ground. It does not need to be level, but within +- 10 degrees.

It also calibrates the gyros on start-up, so you may get a error message if it is moved to much around when connecting the battery. Disconnect and reconnect to get rid if that message. This calibration is not important, but it will affect the angles being shown on the SAFE screen. They may be wrong. Arm and disarm if you want to see the correct ones.

The default self level gain where determined on a HK H.A.L quad.

During prolonged looping, flipping and high angle sport flying the KK2 may lose its bearing of the up and down direction and not keep level when self-level is turned on, especially if the KK2 experiences a temperature change since the last arming. Land and re-arm to fix this, no need to disarm first.

Nerd-info:

To accomplish this:

Added a second math library to handle the 3D vector rotations. This library is 8.24 signed fixed point, written specially for this case.Due to the high resolution it is not necessary to normalize the 3D vector.
The 3D vector is a Quarternion without the rotation parameter, aka direction vector. This vector always point straight up.
The Euler angles (roll/pitch) where extracted from the 3D vector in a simplified way, no memory for a ATAN2 and ASIN2 function. They will show wrong values past +-90 degrees, but this does not affect the performance.
The accelerometers is only used when roll and pitch angles is inside +-10 degrees and vertical acceleration is inside 0.7 to 1.3G to remove any drift on the direction vector. Therefore long periods without level hovering may cause the vector to drift.

And I am happy I stayed on the assembly road, I feel home then.