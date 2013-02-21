Here is version 1.4

Changes:

1: SW LP-filter on the accelerometers.

2: Widened the correction limits to +-20 degrees.

3: Use accelerometer generated Euler angles instead of 3D vector generated angles for the correction check as suggested by Scolton. I think this one really did the trick.

4: Widened the vertical acceleration check to 0.5 - 1.5g.

5: It does not show the Euler angles on the safe screen until gyros has been calibrated to avoid confusion.

Updating from V1.3 to V1.4 does not change your settings.

Now it performs much better, it did not lose its UP direction at all, except for the special case of the toss test where the rotation rate exceeded the maximum that the gyros can handle. This will not happen during flight.