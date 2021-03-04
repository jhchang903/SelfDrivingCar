# Motion Planning

The goal of this project will be to have a functional motion planning stack.\
The self-driving veihcle has to track the deired path while avoiding static vehicle and follow a preceding vehicle once they are getting closer.

Finite state machine decides the state (or mode) which vehicle will perform for the next step.\
It includes three states, including "Follow lane", "Decelerate to stop", and "Stop".

When the state is Follow lane, the vehicle will check the desired waypoints and select the one that is closest to its desired lookahead distance.\
After the desired waypoint for the next step is picked, Conformal lattice is applied to plan several trajectoies whose ends are close to that desired waypoint.\
Finally we use an objective function to decide the best trajectory that helps the vehicle to avoid collision.

The framework of this project is shown in the figure below.\
<img src="https://github.com/jhchang903/SelfDrivingCar/blob/master/C4_Motion_Planning/c4_struct.jpg" width="800">