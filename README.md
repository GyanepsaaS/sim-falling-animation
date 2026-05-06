# sim-falling-animation
Simulating controlled falling motion of a simplified humanoid model for 3d animation

## Abstract
This project uses PyBullet to simulate controlled falling motion for a simple, 3-link humanoid robot model, in order to achieve stylised yet accurate falling mechanics for 3d animation. Parameters like the initial state or initial velocity can be provided to the model, and the final simulation can be ported over to Blender using the PyBullet Blender Recorder. LQR is used as the controller for balancing.

## Introduction
The aim of this project is to use simulation to help animate falling motion.
Animating can be very time-intensive, and getting the dynamics of physics-heavy behaviours like falling can be difficult to do entirely by hand, which makes approaches like simulation or motion capture useful tool. However, relying largely on motion capture data or simulating a motion with minimal adjustment can reduce the amount of creative freedom available to the animator in making stylised animations.
By using a simulation-based approach that is tailored to a specific action, falling, and with customisable parameters, this approach could work in helping create a more realistic falling animation than just posing the system manually, while also not sacrificing the potential for more
stylisation and creative freedom.
The approach to this was informed by previous works using simulation approaches as part of animating or controlling humanoid figures, e.g. [1] and [2]. 

## Set up and modelling
The model used to simulate this was a 3-link robot with a torso and 2 legs (see image below from PyBullet for reference). This was set up in PyBullet with appropriate parameters - mass was assigned based on the average human weight of 60kg, in a standard ratio roughly matching body weight distribution of 60%-20%-20% for the torso and limbs for maximum accuracy.
![img1](src/img1.png)

The state of the model was defined using:
- 3 rotations (torso, l_leg, r_leg)
- 3 angular velocities (torso, l_leg, r_leg)

The goal position was defined as the unstable equilibrium where all rotations were at 0, i.e. the biped is standing fully upright.

Using the standard LQR formulation, $\dot{x}$


[1] Marco, Y. Abe, and J. Popović, “Interactive simulation of stylized human locomotion,” DSpace@MIT (Massachusetts Institute of Technology), Aug. 2008, doi: https://doi.org/10.1145/1399504.1360681.
‌[2] K. YAMANE, J. K. HODGINS, and H. B. BROWN, “CONTROLLING A MOTORIZED MARIONETTE WITH HUMAN MOTION CAPTURE DATA,” International Journal of Humanoid Robotics, vol. 01, no. 04, pp. 651–669, Dec. 2004, doi: https://doi.org/10.1142/s0219843604000319.
‌
