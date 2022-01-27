# HW1 - Jake Smith
## Challenge Questions

1. Show, based on the flux with depth, that the model is steady state.  Repeat this for a homogeneous and for a heterogeneous column.

- As can be seen on the submitted figures, both flux plots demonstrate that flux remains the same at all points in the column. This demonstrates that the model is steady state, as flux is not changing.

2. Show that the steady state flux agrees with the direct calculation based on the harmonic mean average K.  Write the equation defining the direct calculation of the flux.

- The equation that defines the direct calculation of flux is Darcy's Law, written as q=-K(dh/dL)

- Using the harmonic mean of the heterogenous model, we calculate a K of 0.000833 m/day. Plugging this into Darcy's Law for K gives us a flux of 0.001389 m/day, using the value of (100/60) for (dh/dL). Our steady state flux plot shows a straight line at exactly this value, so the harmonic mean calculation agrees with the model's iterative solution and plot.

3. Show the steady state head profile for a column with approximately equal-thickness layers that have different K values.

- Please see attached heterogenous profile image from earlier submission (sorry, I am not sure how to insert images into markdown files)
  
4. Use the head profile to explain WHY the equivalent hydraulic conductivity, Keq, is closer to the lower of the two K values.

- I think of this as a simple matter of the pieces being limited by the slowest moving part. The lower conductivity layer will be the limiting factor for the rest of the water moving through the column. It's essentially setting the speed limit for our column.

## Discussion Questions

1. What are boundary conditions?  Answer this both conceptually and mathematically.

- conceptually, the boundary conditions define the end of our "box" as far as our spatial dimensions are concerned. Mathematically, this would be our upper and lower limit for z, or L. Our other boundary condition is Head. Our h value sets the hydraulic properties of our column, mathematically we are telling the model how to compute the dh component within Darcy's Law.
  
2. What are model parameters?  How do they (and don't they) represent the actual subsurface?

- Model parameters are our input variables. For the Box Model our parameters include column length (z), hydraulic head (h), and hydraulic conductivity (K). 

- z represents the vertical domain of our model, while hydraulic head is exactly that. In our model, unlike reality, they only reflect the value assigned to particular cell in our model. Soil isn't made up of distinct cells like this, and is a continuous gradient in the physical world. Hydraulic condctivity represents how quickly water can move within our soil column under saturated conditions. In our model, we idealize this into simple, finite layers with no variation within each cell. In reality, K is extremely variable, even throughout a soil column of the size in our Box Model.
  
3. What are steady state conditions and how can they be identified from the Excel model results?

- Steady state means that there is no change in storage of our system. simply put, the water going in is equal to the water going out. It can also be defined as constant flux within the confines of our model. We can identify this by observing the flux plot next to our head profile. For steady state flow we should see essentially a vertical line on the plot, meaning flux is constant. 
  
4. Can you imagine how the model inputs could be stored in separate files rather than other spreadsheet cells?  Describe the flow of information from a file that describes the other files that contain model-specific information about the system. 

- I think that this makes sense to me. Basically, I would envision that each file is text based, using tabs and spacing to deliniate cells from one another, while another file might control what properties are applied to each "cell" in the other text file.Perhaps this is done by a master file telling a program like modflow where to find all the others, kind of like a master directory that handles all the queries.
  
5. What is an iterative solution?  Can you explain it to a hydrologist who is not a modeler?  Can you describe (or imagine) how Excel finds the solution?

- An iterative solution means you are plugging in an educated guess for a variable to solve an equation, than using that previous result to refine the next solution. The goal is to pick an initial guess that allows your iterations, multiple solution steps, to eventually converge onto the correct answer. In Excel, you basically provide the equation, and set it equal to a value you desire, Excel will then iterate the equation systematically to get you as close as possible to what you want. 

6. What is a direct solution?  What are its (dis)advantages compared to an iterative (numerical) solution?

- A direct solution is simply solving an equation for one of your variables. You give a formula, tell Excel what input variables are, and it spits out a single solution. There is no iteration required. One advantage to this is that it is much less computationally intensive, and is a better setup for simple, linear equations. A disadvantage is that this method can often not solve complex, or non-linear problems like an iterative process can do.