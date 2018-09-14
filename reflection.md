Reflection of CarND-MPC-Project

The Model #######################################################################################
Student describes their model in detail. This includes the state, actuators and update equations.
In MPC.cpp I implemented MPC. First I update the cost, which is stored in the first element of fg.
The cost based on the reference state will be added and the use of the actuators and the value gap
between sequential actuations will be minimized.
Then more constraints will be written in fg.
The starting values of x, y, psi, v, cte are and epsi are from the vector of variable values.
The following values in the timestep length have to be calculated in lines 79 - 121.

Timestep Length and Elapsed Duration (N & dt) ###################################################
Student discusses the reasoning behind the chosen N (timestep length) and dt (elapsed duration between timesteps) values.
Additionally the student details the previous values tried.
I use a timestep length of 15 because this was my best value.
A shorter timestep length of 10 caused a inaccurate calculation in the bends. The car drove more to the outside.
A longer timestep length of 20 caused the car to leave the track.
I use a elapsed duration between timesteps of 0.1 because this was my best value.
A shorter elapsed duration between timesteps of 0.05 caused a disturbed driving of the car.
A longer elapsed duration between timesteps of 0.2 caused the car to leave the track.

Model Predictive Control with Latency ###################################################
Student provides details on how they deal with latency.
I leaved the latency value at 100ms.
