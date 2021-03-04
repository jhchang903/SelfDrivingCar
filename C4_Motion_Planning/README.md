# Motion Planning

The goal of this project will be to have a functional motion planning stack.\
The self-driving veihcle has to track the deired path while avoiding static vehicle and follow a preceding vehicle once they are getting closer.

### Finite state machie
Finite state machine decides the state (or mode) which vehicle will perform for the next step.\
It includes three states, including "Follow lane", "Decelerate to stop", and "Stop".

### Follow lane and local planner
When the state is Follow lane, the vehicle will check the desired waypoints and select the one that is closest to its desired lookahead distance.\
After the desired waypoint for the next step is picked, Conformal lattice is applied to plan several trajectoies whose ends are close to that desired waypoint.\
Finally we use an objective function to decide the best trajectory that helps the vehicle to avoid collision.

### Framework
The framework of this project is shown in the figure below.\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C4_Motion_Planning/c4_struct.jpg" width="800">

# Simulation in CARLA

## Obstacle avoidance 
### Obstacle avoidance 
The vehicle tries to avoid the static obstacle and keep tracking the lane after it passes the obstacle\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C4_Motion_Planning/modify_traj.gif" width="800">\
### Planning in real time
The vehicle plans trajectiries and chooses the best one in real time.\
The green curve is the desired path.\
The cross symbals (+) represent the obstacl on the road.\
The orange curve is the actual trajectory that the vehicle has drived through.\
The blue and red curves are the candidate trajectories that the vehicle planned.\
The blue ones are feasible because it avoids the obstacle while the red ones are not feasible.\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C4_Motion_Planning/traj.gif" width="800">


## Follow the lead vehicle
If the time-to-collision is less than its threshold, the vehicle will slow down from its own desired speed to an appropriate speed so that it won't collide with the lead vehicle.\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C4_Motion_Planning/adj_speed.gif" width="800">


### Things to improve
1) Even though the vehicle successfully avoid the obstacle on the road, they are still too close. (Adjust the objective function weight)
2) The performace of tracking is not good enough because the tracking term in the objective function dependes only on the endpoint within a certain time horizon. This results in a weird turning trajectory. (Adjust the tracking term in the objective function)
