<iframe width="560" height="315" src="https://www.youtube.com/embed/l-wUKu_V2Lk?si=EDmB1RcpfnzhesQX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
- crisp frames, no motion blur etc.
- treat city as character
- use mis-print color dots to reduce camera focus 
- color gblobs in distance of night city like rain.bw painting to abstract away detailn
- pop impact frames hand drawn entirely to create visual alnguage
- line work use ML and referenced drawings over 3d model pose to guess placement
	- LIKE JOEL HAVER!!!
- camera on ones, but characters on twos
	- multiple characters on twos, but out of sync to story tell until same sync when miles learns
- different physics for noir, penny, and peter porker diff cartoony dimensions
- end game particle beam colors shifted by spider verse

18:12
### Numerical Methods
- Approximate by summing line segments
- Build lookup table mapping parameter u to arc length s
- ![[bf9b4adcbabcb26dddf0def28703a774_MD5.jpeg#invert]]
- approx. between u entries by rounding
	- u = 0.73    which is technically index ==.73/.05 = 14.6==
	- ith row = round that up = 15
	- 15th row of table for u = 0.75 = 0.959
- alt: interpolation
	- round down :  14 so 0.944
	- for fractional part, interpolate:    0.6 x (0.959-0.944)
	- add together: 0.953
- sampling error varies, so adaptive linear??
	- given some error threshold (acceptable diff):
	- check subdivide, if diff exceeds threshold, keep subdividing. 
	- ![[a069d7403931317f8b03666c5869fd8c_MD5.jpeg#invert]]
	- then write to fixed-len table
- sampling with curved segments not linear? ==Gaussian quadrature ==
	- approximates integrals
	- ![[92ac674a51c2a820a58c05d986bf929d_MD5.jpeg#invert]]v
	- tabulates the sampling of the value and gives approx value
	- also can be adaptive: monitor errors and subsample
	- same as linear interpolation lookup table but use gaussian to calculate fractional part

## Inverse Arc Length Problem
- Goal: Find u given arc length s,  u(s)
	- why? find position @ t  = P(u(s(t)))  where s(t) is time curve
	- s(2s) = 5 units (at 2 seconds, be 5 units along curve)
	- u(5 units) = 0.7 (to be 5 units along curve, we need u = 0.7)
	- P(0.7) = (10, 5, 3) (at parameter 0.7, position is (10,5,3))
- Root finding methods:
- we want u(s):  
	- we have: $s(u)=length(u0, u)$
	- move to one side: $f(u) = s - length(u0, u)$ = 0
	- **Bisection**: 
		- simply plug in trial-error
		- Bracket root with two guesses, then binary search for zero (w/ error threshold)
	- Newton-Raphson: Use derivative to converge
		- approx by iteratively using first two terms (pos + tangent) of inifnite taylor expansion
		- ![[a4d88bba77f0da9572798f60dd512bb2_MD5.jpeg#invert]]
		- 2. **Find the tangent line** at random guess $x_n$
			- $y = f(x_n) + f'(x_n) (x - x_n)$  
		- 3. **Find where the tangent line crosses the x-axis** (y=0)
			- $0 = f(x_n) + f'(x_n) (x - x_n)$  
			- Rearranging:  
			- $x = x_n - \frac{f(x_n)}{f'(x_n)}$
		- therefore iteratively do the following to converge to root: $$ x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)} $$
	- Secant: Approximate derivative numerically
		- when you don't know the 1st deriv of function (i.e. given black box for pos)
		- approx. derivative w/ two previous points: $$ f'(x_n) \approx \frac{f(x_n) - f(x_{n-1})}{x_n - x_{n-1}} $$ plugging in newton-raphson: $$ x_{n+1} = x_n - \frac{x_n - x_{n-1}}{f(x_n) - f(x_{n-1})} f(x_n) $$
## Speed Control

-
- 
### Easy In/Easy Out
-  i.e. s(t) = distance along curve at time t
	- i.e. portion of sine function = $(sin(\pi t - \pi/2) + 1)/2$
	- ![[8614046bf33a97fdd3fdddfd6175b8b6_MD5.jpeg#invert]]
		- must normalize total distance to 1.0
	- Combined sinusoidal and linear segments
		  - ![[dce0c3924cf5f2462acbc13120636869_MD5.jpeg#invert]]
		  - must ensure continuous derivative at connection pts k1 and k2
	  - Parabolic (constant acceleration/deceleration)
		  - cheaper than sin
		  - given desired t1, t2, and v0:
		  - ![[a390f3821fbf014e8081d3a8ed81a8bc_MD5.jpeg#invert]]
		  - total distance traveled = integration of velocity curve (area)
### Velocity Control
- Can use arbitrary velocity curves (e.g. splines)
- Must maintain average velocity for consistent distance

## Path Following
### Frenet Frame (diff. geometry)
- i.e. plane cannot just follow path, must rotate in that direction
- Moving RH coord system moves/orients along path (call axis u,v,w)
- Computed from:
	- P(t) is curve
	- forward direction w = tangent of curve (P'(t))
	- perpendicular to curv(inward to concave) & tangent: u = w × P''(t)
	- v = w × u
	- ![[71d650b934db2b0229030a887f257c8d_MD5.jpeg#invert]]
	- must normalize vectors to describe coord sys
	- can approx deriv and curv
### Limitations & Solutions
- Discontinuous curvature at joins (jump in w)
- Issues with straight segments (P''(t)=0, arbitrary 360 orientation around w)
	- Solution: Lerp axis before/after straight part
- Camera motion problems
	- usually demands C2 continuity (otherwise motion sick POV)
	- not really facing tangent like plane, but looking at subject
	  - **Solution**: Use center of interest (CoI)
		  - w = CoI - P(t)
		  - u = y-axis × w
		  - v = w × u
	  - ![[Pasted image 20250217174858.png#invert]]
- ==SEE TEXTBOOK? for neg w?==