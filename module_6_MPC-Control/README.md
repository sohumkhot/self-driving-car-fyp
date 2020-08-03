# MPC-Control

## Introduction
This is my solution to Model Predictive Controller Project in which the challenge is to drive a car around the track in simulator.

* Tested on Ubuntu 16.04, HP Omen 15 2019
* GPU: GTX 1650
* CPU: i7 9th Gen

# The Model

## State Variables
* px: current location in x axis of global map coordinate system
* py: current location in y axis of global map coordinate system
* psi: current heading of the vehicle
* v: current velocity of the vehicle
* cte: cross track error, which is difference between our desired position and actual position
* epsi: difference between our desired heading and actual heading

## Actuations
* delta: this represents the steering angle by which we will turn our vehicle. The angle is restricted to be between -25 and 25 degrees.
* a: this is the throttle or brake value which represents the acceleration or deacceleration of vehicle. The simulator expects values between -1 and 1. Negative values represents brake while positive values represent throttle.

## Kinematic Model
```
px` = px + v * cos(psi) * dt

py` = py + v * sin(psi) ( dt)

psi` = psi + v / Lf * (-delta) * dt

v` = v + a * dt

cte` = cte - v * sin(epsi) * dt

epsi` = epsi +  v / Lf * (-delta) * dt

where Lf - Distance between center of mass and axle
```

Also 
```
cte = py_desired - py

epsi = psi - psi_desired

py_desired = f(px)

psi_desired = atan(f`(px))

where f is the third degree road curve function and f` is the derivative of f
```
# Timestep Length and Elapsed Duration (N & dt)

* N: This represents how many states we look into future.
* dt: This represents in how much time we expect changes in the environment

If N is too small, we cannot predict the future well. If N is too large then we may plan for a long future which not be what we are expecting. **The values for N and dt are 10 and 0.1 respectively.** These values were just a part of hit and trial process. I tested with 6/0.5 ; 8,0.25 ; 15,0.05 also in order to fix 10 and 0.1.

# Polynomial Fitting and MPC Preprocessing

* Transformation to Vehicle Coordinates: the waypoints provided to us are in global coordinate system so we have to convert them to vehicle coordinates. This simplifies the process as vehicle's x and y coordinates are now at the origin (0, 0) and the orientation angle is also 0.
* I used a 3rd order polynomial because it is known to fit most of the roads. Using a smaller order can result in underfitting while using a higher order can result in overfitting.

# Model Predictive Control with Latency

* We have to take in account 100ms latency delay as one of the challenges in the project.
* In actual life, there is usually a latency bewteen the commmand issue time and execution time.
* To compensate the latency, I updated the vehicle state by an latency time before feeding it into the MPC solver.
* As a result the solution from the solver - steering and throttle better account for the current state of the vehicle.
* See lines 132-144 in the main.cpp
