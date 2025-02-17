---
publish: false
Date Created: "02-16-2025 10:10"
---
more smoothnes
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
HERMITE
- given start & end pts + start & end velocities
- auto calculates accel and jolt for physics sim
	- P(0) = P0
	- P(1) = P1
	- P'(0) = v0
	- P'(1) = v1
	- solve for P(t) = at^3 + bt^2 + ct + d
- 