---
publish: false
Date Created: "02-16-2025 10:10"
---
# more smoothness
- cubic bezier:  up to C1 cont (any higher = lose too much control)
- hermite: interpolate up to C1 cont. (curve & tangent)
- catmull-rom splines: also C1
- b-spline: ==approx. not interpolating ctrl points== C2 (+curvature)
	- nerbs: more for geometric surface design ==DEMO==
		- can reproduce conic sections (i.e. exact spheres)

Ch 5 Extended Universe
<iframe width="560" height="315" src="https://www.youtube.com/embed/jvPPXbo87ds?si=us8REvd1JolQ8fSA&amp;start=2366" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe> 
(until 1:03:50)
- limits to bezier curve's other two ctrl pts (only two endpts)

## Hermite

- given start & end pts + start & end velocities (lots of velocity ctrl for easy C1 cont.)
- auto calculates accel and jolt for physics sim
	- P(0) = P0
	- P(1) = P1
	- P'(0) = v0
	- P'(1) = v1
	- solve for P(t) = at^3 + bt^2 + ct + d
- ![[Pasted image 20250217084120.png#invertW]]

## ==CARDINAL SPLINE== (create own velocities given pts)
- C1 and G1 continuous
- each pt take neighboring pts vector and use as pt's velocity
- ![[78edcd0aac7a3044604929b848e77db7_MD5.jpeg#invertW]]
- scale "tension" factor to adjust magnitude of the velocities
- high scale = relaxed
- scale = 1 = bumpy
- low scale = lerp
- scale = 0.5 = comfortable smooth = ==CATMULL-ROM SPLINE== (C1 and G1 cont. )
	- ![[cb59177939a2f614f1a60aa227cb3fbb_MD5.jpeg]]
- ![[6c63797cf6545a990de90de1ab4a8bf6_MD5.jpeg#invertW]]

## B-SPLINE
solving for C2 continuity
but curve doesn't touch any of the ctrl points (sacrifice for C2)
also G2 cont.
still have local control
generalized: ==if spline of order M, = C(M-2) ==
![[0244350c56c0851b4078616dcba8bd40_MD5.jpeg]]
## Summary
similarities:
- cubic
- assumes uniform t (0<=t<=1)
- all about connect & transformation of ctrl pts NOT final spline itself

Uniform Cubic Splines
each with non-uniform (at diff times) and higher degree variations
==NURBS: ==b-spline **rational** = ctrl weights of individual ctrl pts
- even useful in colors! rgb(0,0,0) as 3d ctrl points to map image

| Type            | Deg. | Cont.   | Tangents | Interpol. | Use cases                                                                                   |
| --------------- | ---- | ------- | -------- | --------- | ------------------------------------------------------------------------------------------- |
| **Bézier**      | 3    | C⁰ / C¹ | manual   | some      | shapes, fonts & vector graphics, sharp cusps, hearts, etc.                                  |
| **Hermite**     | 3    | C⁰ / C¹ | explicit | all       | animation, physics sim & interpolation, most common for animation (scale, angle, pos, etc.) |
| **Catmull-Rom** | 3    | C¹      | auto     | all       | animation & path smoothing, convenient focus on shape without defining tangents             |
| **B-Spline**    | 3    | C²      | auto     | none      | curvature-sensitive shapes & animations, such as camera paths                               |
| **Linear**      | 1    | C⁰      | auto     | all       | dense data & interpolation where smoothness doesn't matter or piecewise sampling approx.    |
## Interpolation w/ B-Splines

Goal: generate new control points from points you want to interpolate
constraints?

![[Pasted image 20250217095556.png#invert]]

Solve for c (new control points)
![[472fb787d698459b9e5a31dcbfc640fe_MD5.jpeg#invert]]
if 6 ctrl pts, 6x6 matrix. if 100, 100x100... but always diagonal symmetric pattern
**A** **c** = **y** 
**c = A^-1 y**  ==LU-decomp== alg
- split matrix into product of two trivial-to-solve matricies (lower & upper triangles)
- forward substitution & back substitution (or diagonal too LDU = ==koleski==)
- 
observations
- get the zero in sys equations because evaluating basis functions beyond t range
- if put more contrl pts than constraints, no longer 6x6 square matrix
	- need more constraints i.e. velocity/tangent to eliminate DoF
	- or do pseudo-inverse to handle non-square matrix
- 

## closed splines
- bezier: add curve w/ last pt == first pt
- hermite: same as bezier
- b-splines:  $P0....PL + P0..P_(m-2)$
	- repeat first m-1 ctrl pts 


local control: basis functions drop off quickly even if global

efficient spline evaulation: 
- sub-divide splilnes (more for geometric design)
- Horner's rule:
	- instead of $a_i (t - t_i)^3 + b_i (t - t_i)^2 + c_i (t - t_i) + d_i$
	- do storing vars / factoring:  $x = t-t_i$
		- $((a_i x + b_i) x + c_i) x + d_i$


# Motion Curves
- examples (no physics)
	- obj pos (x,y,z splines)
	- simple angle joint(1 spline)
	- complex joint (2+ splines)
	- scale (1 or x,y,z splines)
	- color (r,g,b splines)
- problem: want to manipulate time/speed too:
	- time as motion curve, and use P(u(t)) instead of P(t)
	- curve for time: u(t) 
	- can even have unique time curve for each var (angle, color, pos, etc.)
- still: difficult to find a u for constant velocity along curve
## arc length parameterization

### analytically (integral):
- way too hairy for cubic polynomials
- 3 curves for pos P: (X(u), Y(u), Z(u)) so
$$
s(u) = \int_{u_1}^{u_2} \left| \frac{dP}{du} \right| du
$$
$$
\left| \frac{dP}{du} \right| = \sqrt{\left( \frac{dX}{du} \right)^2 + \left( \frac{dY}{du} \right)^2 + \left( \frac{dZ}{du} \right)^2 + \cdots}
$$
Example of analytic with parametric circle:
 $[X(t), Y(t)] = [R \cos(t), R \sin(t)]$
 
 1. derivatives: $$( \frac{dX}{dt} = -R \sin(t) ) - ( \frac{dY}{dt} = R \cos(t)  $$
 2. substituting into differential arc length (vector norm) formula: $$ds = \left| \frac{dP}{dt} \right| = \sqrt{ \left( \frac{dX}{dt} \right)^2 + \left( \frac{dY}{dt} \right)^2 } $$
$$ ds = \sqrt{ (-R \sin(t))^2 + (R \cos(t))^2 } = \sqrt{ R^2 (\sin^2(t) + \cos^2(t)) } = R dt $$
 3. integrating: $$ s(t) = \int_{0}^{t} R dt = R \times (2\pi - 0) = 2\pi R $$ 
### numerically (approx)
![[Pasted image 20250217104913.png#invert]]
