# CS 174C Midterm Exam Review  

## 1. Animation Principles  
- [ ] Understand them  
- [ ] Remember a few  

## 2. Math Background  
- [ ] Vectors  
- [ ] Coordinate systems (frames)  
- [ ] Affine transformations  
- [ ] Transformations as a change of basis  

## 3. Rotation & Parameterization  
- [ ] Euler angles (rolls)  
	- [ ] Gimbal lock  
- [ ] Quaternions  
	- [ ] Quaternion operations  
	- [ ] Rotation with quaternions  

## 4. Parametric Curves  
- [ ] Polynomial curves  
	- [ ] Bezier curves  
		- [ ] DeCasteljau: 4 ctrl pts (cubic) as nested lerps  
		- [ ] Bernstein: polynomial coefficients influencing Point (weighted sum)  
		- [ ] Polynomial Coefficients: factor by t not P  
		- [ ] Matrix form separates "magic numbers" aka M  
- [ ] Cubic curves  
	- [ ] From constraints  
	- [ ] Hermite  
	- [ ] Continuity  

## 5. Piecewise Cubic Curves (Splines)  
- [ ] Hermite splines  
	- [ ] Breaking tangent continuity  
- [ ] Catmull-Rom splines  
- [ ] B-splines  

## 6. Motion Curves  
- [ ] Introducing the “time” concept  
- [ ] Arc-length parameterization  
	- [ ] Approximating arc length  
		- [ ] Arc length table  

## 7. Ease-in / Ease-out  
- [ ] Ease() functions  
	- [ ] Sinusoidal  
	- [ ] Sine-line-sine  
- [ ] Control via distance  
- [ ] Control via velocity  
- [ ] Control via acceleration  

## 8. Particle Systems  
- [ ] Uses, particle types, and properties  
- [ ] Kinematic (velocity field) particle motion  
- [ ] Dynamic particle motion  
	- [ ] Mass  
		- [ ] Momentum  
	- [ ] Force  
		- [ ] Gravity  
	- [ ] Newton’s law of motion  

## 9. Mass-Spring-Damper Systems  
- [ ] Forces on particles  
	- [ ] Spring forces  
	- [ ] Damper forces  
	- [ ] Constants (stiffness, damping)  
		- [ ] Simple damped harmonic oscillator  

## 10. Numerical Solution of Equations of Motion  
- [ ] First order systems of ODEs  
- [ ] Second order systems of ODEs  
- [ ] Explicit Euler integration (benefits and drawbacks)  
- [ ] Midpoint integration  
- [ ] Symplectic Euler Integration  
- [ ] Verlet Integration  
- [ ] Implicit Euler integration (benefits and drawbacks)  

## 11. Collisions  
- [ ] Collision detection  
	- [ ] Determining penetration into geometry  
- [ ] Collision resolution  
	- [ ] Newtonian elastic and inelastic collisions  
	- [ ] Penalty method  

## 12. Friction  
- [ ] Coulomb friction model  
- [ ] Static Friction  
- [ ] Sliding Friction  

## 13. Articulated-Body Kinematics  
- [ ] Joints  
- [ ] Hierarchies of links and arcs (joints)  
- [ ] Transformation order  
- [ ] Forward kinematics  
- [ ] Inverse kinematics  
	- [ ] Jacobian, controlled Jacobian, JacobianT, cyclic coordinate descent (CCD) methods  

## 14. Motion Capture  
- [ ] Benefits and drawbacks of the different mocap technologies  
- [ ] Passive optical mocap is the dominant one  
	- [ ] Processing the images / data prep  
	- [ ] Camera calibration  
	- [ ] Marker 3D position estimation  
	- [ ] Fitting the articulated skeleton  
- [ ] Manipulating the mocap data  
	- [ ] Signal processing, retargeting, motion graphs  

## 15. Rigid-Body Dynamics  
- [ ] Definition of a rigid body  
- [ ] Position and orientation  
- [ ] Linear and angular velocity  
- [ ] Force and torque  
- [ ] Mass, center of gravity, and the inertia tensor  
- [ ] Equations of motion  
- [ ] ~~Multibody dynamics~~  
- [ ] ~~Full and reduced coordinates approaches (benefits and drawbacks)~~  
