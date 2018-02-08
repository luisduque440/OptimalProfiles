# Newtons problem on optimal profiles
In Principia Mathematica, Newton proposed the problem of finding the profile of the body that gives minimal (aerodynamic or hydrodynamic) resistance to the motion. A very complete survey of the state of the art of this problem can be found in Buttazzo’s paper [1].

Even though this problem is very old, it is still not known which one is the best profile. For several centuries it was believed that Newtons solution to this problem was indeed the optimal profile when the domain was a unitary ball (see Figure 3.4 in [1]), but in the 90s, it was proved both computationally and theoretically that optimal solutions to this problem cannot be radially symmetric and hence Newton’s solution was wrong. 

In the project NewtonProfile.ipynb , I implemented a greedy numerical approach for finding the optimal profile when the domain is a square. 

# My approach:
The main difficulty when implementing these simulations was the following: Newtons functional only has a physical meaning when the surface involved is concave (see Equation 3.2 in [1]). 

In order to produce convex surfaces (see method Profile.mutate() in NewtonProfile-SquareDomain.ipynb ) I used the fact that every convex function can be written as an infimum of countably many planes. 

Once I was able to generate convex surfaces using this trick, finding the numerical solution to the problem was a matter of implementing Newtons Functional (see method Profile.resistence()) and minimizing it in a greedy way (see the methods ImproveProfile() and ImproveProfile())

# The solution:
I want to point out that the best solutions found when running the file NewtonProfile.ipynb are indeed very similar to the screwdriver shape found by Guasoni (see Figure 3.7 in [1]) in the case when the domain is a Ball.



# References:							
[1] G. Buttazzo, A. Frediani (eds.), Variational Analysis and Aerospace Engineering, 33 Springer Optimization and Its Applications 33, DOI 10.1007/978-0-387-95857-6 3, c Springer Science+Business Media, LLC 2009.  
https://link.springer.com/content/pdf/10.1007/978-0-387-95857-6_3.pdf	
