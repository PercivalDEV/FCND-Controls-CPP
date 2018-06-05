# The C++ Project Write Up Readme #
All tests passed, my writeup is below.

I implemented the various controllers and passed the scenarios with tuning parameters inside the projectc code. 

Quick explanation of how the controllers work. We start off by controller each individual thrust command. Front Left, Front Right, Read left and Rear right. This force is calculated as going upward. Roll is generated from opposing propellers to produce this movement. Pitch is generated by the front two propellers with missing thrust from the back propellers. Yaw is generated by a mismatch by thrust along the z-axis by reactive force. 

<b>Body Rate Controller</b>

Implemented - Line [112](https://github.com/PercivalDEV/FCND-Controls-CPP/blob/be1755a0641fd56402ffecbc7977f3c46d6d351a/src/QuadControl.cpp#L112)

<b>Roll Pitch Controller</b>

Implemented - Line [123](https://github.com/PercivalDEV/FCND-Controls-CPP/blob/be1755a0641fd56402ffecbc7977f3c46d6d351a/src/QuadControl.cpp#L123)


<b>Lateral Controller</b>

Implemented - Line [216](https://github.com/PercivalDEV/FCND-Controls-CPP/blob/be1755a0641fd56402ffecbc7977f3c46d6d351a/src/QuadControl.cpp#L216)

<b>Altitude Controller</b>

Implemented - Line [146](https://github.com/PercivalDEV/FCND-Controls-CPP/blob/be1755a0641fd56402ffecbc7977f3c46d6d351a/src/QuadControl.cpp#L146)


<b>Yaw Controller</b>

Implemented - Line [72](https://github.com/PercivalDEV/FCND-Controls-CPP/blob/be1755a0641fd56402ffecbc7977f3c46d6d351a/src/QuadControl.cpp#L72)

<b>Scenario 1</b>

Used to establish that project was usable. 

<b>Scenario 2</b> 

Added: GenerateMotorCommands(), BodyRateControl(), RollPitchControl(). 

I tuned Kp_pqr and Kp_bank to stabilize the rotational motion and bring the vehicle back to level attitude.

Results:

PASS: ABS(Quad.Roll) was less than 0.025000 for at least 0.750000 seconds

PASS: ABS(Quad.Omega.X) was less than 2.500000 for at least 0.750000 seconds

<b>Scenario 3</b>

Added: LateralPositionControl(), AltitudeControl(), YawControl(). 

I tuned Kp_pos_z, Kp_vel_z, Kp_vel_xy, Kp_vel_z, Kp_yaw, and the z component of Kp_pqr to move the drones to their target points.

Results:

PASS: ABS(Quad1.Pos.X) was less than 0.100000 for at least 1.250000 seconds

PASS: ABS(Quad2.Pos.X) was less than 0.100000 for at least 1.250000 seconds

PASS: ABS(Quad2.Yaw) was less than 0.100000 for at least 1.000000 seconds

<b>Scenario 4</b>

Added basic control to AltitudeControl().

I tuned several parameters to help all drones successfully move properly.

Results:

PASS: ABS(Quad1.PosFollowErr) was less than 0.100000 for at least 1.500000 seconds

PASS: ABS(Quad2.PosFollowErr) was less than 0.100000 for at least 1.500000 seconds

PASS: ABS(Quad3.PosFollowErr) was less than 0.100000 for at least 1.500000 seconds

<b>Scenario 5</b>

Tuned to pass test. The first drone is executing FigureEight.tct and the second drone
executing FigureEightFF.txt

Results:

PASS: ABS(Quad2.PosFollowErr) was less than 0.250000 for at least 3.000000 seconds



