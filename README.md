# CarND Extended Kalman Filter Project

This project use Extended Kalman Filter (EKF) to fuse lidar and radar measurement to track the object's position and velocity.

To run this program, use Term 2 Simulator and uWebSocketIO, follow the steps below:

1. cd build
2. cmake .. && make
3. ./ExtendedKF
4. open simulator and select dataset

## Accuracy

* Dataset 1
<img src="https://github.com/jane212/CarND-Term2-EKF/blob/master/output%20images/dataset1.png" width="200">

* Dataset 2
<img src="https://github.com/jane212/CarND-Term2-EKF/blob/master/output%20images/dataset2.png" width="200">

## Algorithm

This program is built on the starter code provided by Udacity CarND team.

Some key modifications are listed below:

* Initialize state and covariance matrix using first measurement;
* Update F and Q by time elapsed;
* Predict state;
* Update measurement for lidar and radar; 
  * Use Hj for radar update;
  * Add a function 'convert2measure' in Tools, to convert state (px, py, vx, vy) into radar measure (rho, phi, rho dot);
  * normalize phi in y to make sure it is within -pi to pi;
* Calculate RMSE;
* Handle small values (close to 0) in denominator.

