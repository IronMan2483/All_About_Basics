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
