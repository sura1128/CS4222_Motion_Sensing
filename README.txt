CS4222 Programming Assignment 1: Motion Sensor Processing
Group 2
Akshat Dubey  A0103516U
Suranjana Sengupta A0102800A

Changes made in source file ShootingAppActivity.java:

Functions Modified:
1. initSensors()
Added and initialized the ACCELEROMETER and GEOMAGNETIC sensors, rawAcclSensor and geoMagSensor. 

2. startSensing()
Registered the abovementioned sensors with the same measurement interval as linear acceleration
and gravity sensors. 

2. onSensorChanged()
Added a case for rotation sensor by extracting values from the accerlometer sensor and geomagnetic
sensor, stored them in an acclMatrix and magMatrix and processing these values. 

Functions Added:
1. processRotValues()
Creates a rotation matrix from the obtained acclMatrix and magMatrix using getRotationMatrix(..), remaps
the rotation matrix to align it with a new coordinate system as specified using the AXIS_Y and
AXIS_MINUS_X values from SensorManager class. Finally, it gets the orientation using the remapped matrix,
which is also the magnetic heading that is converted to degrees (0-360). The shootingRegion (1-8) can be
obtained by dividing this value of shootingDirection by 45 and typecasting it to an Integer. 

The new shootingDirection and shootingRegion are then displayed in detectShootingDirectionAndRegion(..)
within a text view. 