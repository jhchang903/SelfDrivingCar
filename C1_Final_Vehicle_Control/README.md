## Self-Driving Vehicle Control
This project implements a controller for the CARLA simulator.\
The goal is to control the vehicle to follow a race track by navigating through preset waypoints.\
The vehicle needs to reach these waypoints at certain desired speeds, so both longitudinal and lateral control will be required.


### Longitudinal Control
This project uses PID for longitudinal control.\ 
The value of throttle input is presented in percentage.\
No brake control in this project.

### Lateral Control
This project applies Pure Pursuit for lateral control.\
The steering angle is within the range from -1.22 to 1.22 (rad)

## Result

### Trajectory
The figure show below is the simulation result.\
The orange curve is desired trajectory, and the blue curve is the control result (actual trajectory).\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C1_Final_Vehicle_Control/controller_output/trajectory.png" width="700" >

### Steering angle
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C1_Final_Vehicle_Control/controller_output/steer_output2.png" width="400">

### Throttle
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C1_Final_Vehicle_Control/controller_output/throttle_output2.png" width="400">

### Speed Profile
The speed enveloped within the green dash line is acceptable speed.\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C1_Final_Vehicle_Control/controller_output/Speed%20profile.png" width="400">

### Simulation in CARLA
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C1_Final_Vehicle_Control/SimResultGIF.gif" width="400">
