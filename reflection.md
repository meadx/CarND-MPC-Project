Reflection of CarND-MPC-Project

The Model #######################################################################################
Student describes their model in detail. This includes the state, actuators and update equations.
In MPC.cpp I implemented MPC. First I update the cost, which is stored in the first element of fg.
The cost based on the reference state will be added and the use of the actuators and the value gap
between sequential actuations will be minimized. Then more constraints will be written in fg.
The starting values of x, y, psi, v, cte are and epsi are from the vector of variable values. The following
values in the timestep length have to be calculated in lines 79 - 121.
In the Solve function I added the initial values of the independent variables and constraints with the inital state.
The upper and lower limits are from the MPC Quizzes.
In main.cpp I did a coordinate system conversion in lines 104 to 112. Then it is possible to calculate the
cte and epsi with the calculated coeffs. Then I calculate the next state with latency handling and use the
mpc.Solve funkction to get the steering an throttle value.
The steering value has to be multiplied with -1 an divided with by deg2rad(25), so that the values are between -1 and 1.
The steering an throttle value are the first 2 elements in the solve vector. The following values are
the next x and y values, which are used in lines 149 to 152 to print the green MPC predicted trajectory.

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
First I get the values of the last steering angle and throttle value.
In main.cpp I calculate the next state in dt of 0.1 in the lines 125 to 130.
I used the calculations from the lesson without using px, py and psi because of the coordinate system conversion.
The same value of  Lf like the Lf in MPC.cpp is used.
