# CSC417-PBA-Lab

In the class of CSC417, I have implemented few projects on various topics in Physics Based Animation. Here are the summary of each lab:

## [Lab 1: 1D mass-spring System](https://github.com/Winnerrang/1D-Mass-Spring):
In this lab, I implemented a simple 1-D mass-spring system using the Euler-Lagrange Method to derive the equation of motion. For time integration, I implemented various methods, including the forward and backward Euler methods, the 4th order Runge-Kutta algorithm, and the Sympletic Euler Method.

Here is the 1-D system using backward Euler that will create a artificial damping affect.


https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/9baa8050-0cb9-4f10-a18e-e3950fa76534



Here is the 4th order Runge-Kutta algorithm that does not have either damping and exploding effect.


https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/279bd0c1-aca2-4c38-aa5b-5689415681e1



## [Lab 2: 3D mass-spring system for Deformable Mesh](https://github.com/Winnerrang/CSC417-3D-mass-spring/tree/cf402c040133689f67da7b601c8c097dee15f07c):
In Lab 2, I utilized a 3-D mass-spring system to simulate deformable meshes. To formulate the equation of motion, I determined the potential energy, kinetic energy, and their derivative respect generalized coordinate and velocity of the system. For the time integration, I employed the linear implicit Euler method by constructing the stiffness gradient of the system.



https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/135a3b90-8a05-41e0-98ec-d5cc2594afff


## [Lab 3: Deformable Object Simulation using FEM](https://github.com/Winnerrang/CSC417-FEM-Deformable-Object/tree/25a62624c6bb68df1c11d2d3d1ad13fd7c173b88)
Note: The link will go to a different branch in my repository, make sure to change to master branch to see my code.

In Lab 3, I employed the traditional Finite Element Method for simulating a deformable object. By dividing the mesh into numerous finite tetrahedra, I successfully calculated the individual energy, force, and stiffness matrix for each tetrahedron. Subsequently, I combined these to determine the total quantity for the entire object. 

For the calculation of potential energy, I utilized the Neo-Hookean energy density formula, which necessitates the determination of the deformation gradient for each tetrahedron.

In the process of integration, I utilized both the linear implicit method and the implicit method. With the linear implicit method, the operations proceed smoothly, provided there is minimal perturbation of the mesh. However, excessive perturbation can induce an enormous force, leading to the simulation becoming unstable.


https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/20a95c93-fa58-4e04-98ad-9436ac90185e



Things will get worse pretty quickly if your object's stiffness is high.



https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/19fd14e8-5007-4acb-8525-ce8618bdcca9


In the implicit integration process, an energy cost function is defined and optimized using the Newton method to determine the velocity for the next frame. The line search technique is utilized in the Newton method to avoid an increase in energy. An additional comparison is required between the new and old energy levels to ascertain if the new energy is better, which includes checking if the new energy is 'nan.'

This is especially important as high velocities can lead to an inverted (reflected) tetrahedron, resulting in a negative determinant of the deformation gradient and ultimately leading to 'nan' energy. This scenario may occur during the optimization of energy in the Newton method, necessitating careful handling.



https://github.com/Winnerrang/CSC417-PBA-Lab/assets/83567556/8ec82e97-7cec-4e68-9214-389573aaafe6


## [Lab 4: Cloth Simulation using FEM]([https://github.com/Winnerrang/CSC417-FEM-Deformable-Object/tree/25a62624c6bb68df1c11d2d3d1ad13fd7c173b88](https://github.com/Winnerrang/CSC417-FEM-Cloth-Simulation)https://github.com/Winnerrang/CSC417-FEM-Cloth-Simulation)
Still working on it!
