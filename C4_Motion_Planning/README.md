# Motion Planning

The goal of this project will be to have a functional motion planning stack.\n
The self-driving veihcle has to track the deired path while avoiding static vehicle and follow a preceding vehicle once they are getting closer.\n

Finite state machine decides the state (or mode) which vehicle will perform for the next step.\n
It includes three states, including "Follow lane", "Decelerate to stop", and "Stop".\n

When the state is Follow lane, the vehicle will check the desired waypoints and select the one that is closest to its desired lookahead distance.\n
After the desired waypoint for the next step is picked, Conformal lattice is applied to plan several trajectoies whose ends are close to that desired waypoint.\n
Finally we use an objective function to decide the best trajectory that helps the vehicle to avoid collision.\n

The framework of this project is shown in the figure below.
