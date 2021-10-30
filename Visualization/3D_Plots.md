# __3D Plots__

`````````````
from mpl_toolkits.mplot3d import Axes3D

   x, y = np.mgrid[-3:3:30j, -3:3:30j]
   z = (x**2+y**3)*np.exp(-x**2-y**2)
   cmap = 'coolwarm'
   

   fig = plt.figure()
   ax = fig.gca(projection='3d')

   ax.plot_surface(x, y, z, rstride=1, cstride=1, cmap=cmap, alpha=0.5)

   cset = ax.contourf(x, y, z, zdir='z', offset=-0.8, cmap=cmap)

   ax.set_xlabel('$x$', size='xx-large')
   ax.set_ylabel('$y$', size='xx-large')
   ax.set_zlabel('$z$', size='xx-large')
   ax.set_zlim(-0.8, 0.5)
   
   plt.draw()
``````````````

In the following example, a function of two variables is displayed three-dimensionally. In addition, a projection of the function data is shown in the x-y plane. Three-dimensional plots require an import from the matplotlib toolkit, which is done first. Then, the function to be displayed is evaluated on a grid. 
* __np.mgrid[-3:3]__ 
    * x and y axis from -3 to 3 each
* __cmap = 'coolwarm:'__
    * In addition, we choose a color palette to use for both the three-dimensional representation and the projection.
* __rstride=1, cstride=1__
    * arguments rstride and cstride specify the intervals at which intersection lines are drawn relative to the grid width
    * in 3D it is shown as a plane
* __alpha=0.5__
    * In addition to the color channels R, G and B, for example, the alpha channel specifies the transparency of the color. So, in the example, the surface is partially transparent, so it is light grey.
* __ax.set_xlabel 
* __ax.set_zlim(-0.8, 0.5)__
    * z axis starts at -0.8 and ends at 0.5

We represent the projection into the x-y plane with the help of the contourf function, as we have already discussed, but in this example we do not represent contour lines. When used in a three-dimensional representation, we still need to specify the orientation of the project plane using the normal direction zdir and the position using offset. By choosing zdir appropriately, it would also be possible to make projections into the x-z and y-z planes.

Finally, in our example, we set the axis label and extend the range of values of the z-axis to be able to display the projection. Finally, we plot the figure, which here, unlike most of the examples in this chapter, was created in an object-oriented manner.

Translated with www.DeepL.com/Translator (free version)