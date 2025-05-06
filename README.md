# Overview
This repository contains a simple implementation of a reaction diffusion system using the Gray-Scott model. 
The Gray-Scott model is a mathematical model that describes the interaction of two chemical substances that diffuse and react with each other. 
The model is defined by a set of partial differential equations (PDEs) that describe the concentration of the two substances over time and space.
The implementation discretizes the PDEs and simulates the reaction diffusion process on a 2D grid.
## Gray Scott model
In this system, there are two chemical species, u and v, whose reaction can be described as:
The reaction is: 

![image](https://github.com/user-attachments/assets/4ea761fe-e9f6-4282-aa50-2c3a9fc4f110)

The following partial differential equations describe the model:

![image](https://github.com/user-attachments/assets/54671cb2-5df9-47c0-a3fc-45dfc1d587bb)

Where each equation describes the rate of change of the chemical species at a point in space. **Du** and **Dv** are the **diffusion coefficients** that interact with the spatial Laplacian 𝛁2. The reaction term uv2 is a consequence of the stoichiometry of the reaction equation. **F** is the **feed rate** of the chemical species, and **k** is the **kill rate**. For a Tuning pattern to form, it is essential that u diffuses faster than v.

The main file to be run is Turing_pattern_combined.ipynb in the code directory of this repository.


The `create_interactive_simulation()` function creates an interactive plot with sliders to control the parameters.

![image](https://github.com/user-attachments/assets/cd8688d3-5c87-4241-8336-5d182e9a4038)

In addition to the feed rate, kill rate, Du and Dv, we can also change the following:

**Frame**: This slider is essentially a play button. As we move the slider forward, the simulation progresses along time. When the slider is at 0, the perturbations which have been initialized can be seen. When the slider is at its max value, the final pattern is seen.

**Grid size**: This slider allows one to control the spatial extent of the simulation.

**Sample interval**: Since storing the entire simulation is a memory-heavy process, this slider allows one to control how many frames are stored. For example, in this image, every 10th frame is stored in memory.

**Perturbations**: This slider controls the number of perturbations the simulation is initiated with.

**Method**: The simulation can be run either using the Forward Euler method of integration, or the 4th order Runge Kutta method.

**dt**: controls the time step size

**Total time**: the total time of the simulation.



The `simulate_phase_diagram_movie` function creates a animated gif that shows the entire simulation. The gif will be saved in the same directory as code file. It will also output a static plot of the final timepoint.
Some example gifs can be seen in the sample_visualisations directory of this repository.
# Version information
Python: 3.12.4

jupyterlab: 4.3.6

numpy: 1.26.4

matplotlib: 3.8.3

ipywidgets: 8.1.5

ipython: 8.25.0

scikit-image: 0.25.2

pandas: 2.2.2

scipy: 1.12.0

scikit-learn: 1.5.0

seaborn: 0.13.2

## ipywidgets not rendered
ipywidgets requires frontend extensions to render properly. If they're not installed or compatible, the widget won't display. Try installing jupyter locally in the environment and then installing ipywidgets.
