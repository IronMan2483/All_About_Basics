# __Color palette__

Get the color palette in the Matplotlib library:

    named_colors.py 

![colours](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/colour_palettes.png)

You can select a lot of colors by one letter:

`````````
In: mpl.colors.BASE_COLORS
Out: {'b': (0, 0, 1),
         'c': (0, 0.75, 0.75),
         'g': (0, 0.5, 0),
         'k': (0, 0, 0),
         'm': (0.75, 0, 0.75),
         'r': (1, 0, 0),
         'w': (1, 1, 1),
         'y': (0.75, 0.75, 0)}
`````````

* You get blue (b), cyan (c), green (g), black (k), magenta (m), red (r), white (w) and yellow (y) 
* The tuple as the value in the key-value relation, returns the RGB values of each of these colors:         
    #### <span style='color:blue'>__'color': (red value, green value, blue value)__</span>

* white: all three values are at the highest level, so it is 100% or 1 (1,1,1).
* black: all three values are at the lowest level, so it is 0% or 0 (0,0,0).
* for the complementary colors cyan, magenta and yellow are 2 of 3 channels "filled": 
    #### <span style='color:cyan'>__'c': (RED 0, GREEN 0.75, BLUE 0.75)__</span>
    #### <span style='color:magenta'>__'m': (RED 0.75, GREEN 0, BLUE 0.75)__</span>
    #### <span style='color:orange'>__'y': (RED 0.75, GREEN 0.75, BLUE 0)__</span>


* you can get most of the colors by their color name, but to get a full list of the available color names you can do this:

``````````
In: mpl.colors.cnames

Out: {'aliceblue': '#F0F8FF', 'antiquewhite': '#FAEBD7', 'aqua': '#00FFFF',
         'aquamarine': '#7FFFD4', 'azure': '#F0FFFF', 'beige': '#F5F5DC',
         ...
         'violet': '#EE82EE', 'wheat': '#F5DEB3', 'white': '#FFFFFF',
         'whitesmoke': '#F5F5F5', 'yellow': '#FFFF00', 'yellowgreen': '#9ACD32'}
``````````

* Every color has again a RGB value but in this case hexadecimal coded: three 2-digit hexadecimal numbers with values between 0 and 255.

![Diverging, miscellaneous and qualitative colormaps](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/colormaps.png)
![Sequential Colormaps](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/sequential_colormaps.png)

---
---

# __Format the plot__

* Set properties (setp) with .setp() 
    * set the line width for the selected line, here line2

        `
        plt.setp(line2, linewidth=10)
        `
    * set the line color for the selected line, here line

        `
        plt.setp(line1, color='m')
        `
        
        OR
        
        `
        plt.setp(line1, color='#FFC000')
        `
        
        OR
        
        `
        plt.setp(line1, color=(0, 0.7, 1))
        `

    * set the line color for the selected line to grey, here line1

        `
        plt.setp(line1, color='0.5')
        `
    * set the line color for the selected line(s) with mpl.colors.hsv_to_rgb, R/G/B values in % in the brackets

        ```
        plt.setp(line1, color=mpl.colors.hsv_to_rgb((0.3, 1, 1)))
        
        plt.setp(line2, color=mpl.colors.hsv_to_rgb((0.3, 1, 0.6)))
        ```
    * set the line style for the selected line

        `
        plt.setp(line2, linestyle='--')
        `
    * set the stroke length or even define the shape of the stroke ends

        `
        plt.setp(line2, dashes=(4, 2), dash_capstyle='round')
        `

* .cla() for "clear current axes" deletes current plot
    
    `
    plt.cla()
    `

* Define marker points on a line: If you have 2 different lines in a plot, you can select the color of the line and the format of the marker points in 1 bracket for each:
    ```
    plt.plot(x, y1, 'ro-')

    plt.plot(x, y2, 'yD-')
    ```

    * Both lines have the same x axis, so there is 1 x only. But you need to define the y1 or y2 for each line. 
    * <span style='color:red'>'ro-'</span> = __r__ stands for the color RED, __o__ stands for the symbol of the point (here a circle)
    * <span style='color:orange'>'yD-' </span>= __y__ stands for the color YELLOW, __D__ stands for the symbol of a diamond 

* Change size of the marker points
    * Standard marker size is 6

    `
    plt.getp(line1, 'markersize')
    `

    * Change the size
    ```
    plt.setp(line1, markersize=4)

    plt.setp(line2, markersize=10)
    ```

* Marker points dictionary with further formats:
    ``````````
    mpl.lines.Line2D.markers
    
    Out: {'.': 'point', ',': 'pixel', 'o': 'circle', 'v': 'triangle_down',
    ...
    8: 'caretleftbase', 9: 'caretrightbase', 10: 'caretupbase',
    11: 'caretdownbase', 'None': 'nothing', None: 'nothing',
    ' ': 'nothing', '': 'nothing'}
    ```````````

![filled marker](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/matplotlib_filled_marker.png)

![unfilled marker](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/matplotlib_unfilled_marker.png)

---
---

# __Format the axis__

* Format the font size with 2 different possibilities:
    `
    plt.xlabel('t', fontsize='x-large')
    `
    
    OR

    `
    plt.ylabel('cos(t), sin(t)', fontsize=30)
    `
* Format the axis font if a ___greek letter___ or ___mathematical symbol___ is included (use $)

    ```
    plt.xlabel('$t$')

    plt.ylabel(r'$\cos(\omega t), \sin(\omega t)$')
    ```

    OR

    ```
    mpl.rc('text', usetex = True)

    plt.ylabel(r'$\cos(\omega t), \sin(\omega t)$')
    ```
* Define the axis (start and end of the axis) - here start at 4 instead of 0 and ends at 6:
    `
    plt.xlim(4, 6)
    `

---
---

# __Legend__

* Add a label (after the marker format) to prepare the legend
    ```
    plt.plot(x, y1, 'o-', label='Kosinus')

    plt.plot(x, y2, 's-', label='Sinus')
    ```
* Show the legend (last step before plot show!)

    `
    plt.legend()
    `
* If you want to add the location of the legend use loc in round bracket`

    `
    plt.legend(loc='upper right')
    `
* If the legend should be outside of the plot:   
    * legend is placed with the upper left corner slightly outside the upper right edge of the graphic
    * exact point is specified relative to the so-called "bounding box", which has here always the horizontal and vertical length 1, thus is independent of the problem coordinates, which run here in horizontal direction from 0 to 10 and in vertical direction from -1 to 1. 
    * point (1.02, 1) thus lies as claimed slightly to the right of the upper right corner of the graphic
    `
    plt.legend(bbox_to_anchor=(1.02, 1), loc='upper left', borderaxespad=0)
    `
---
---

# __Save the plot as a file__

* graphic (.jpg/.png) 

    `
    plt.savefig('example.png')
    `
* pdf file

    `
    plt.savefig('example.pdf')
