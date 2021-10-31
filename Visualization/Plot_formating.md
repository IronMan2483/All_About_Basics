# __Format the plot: Line__

Set properties (setp) with .setp()

---

## __Set the line width__  

### __set the line width for the selected line, here line2__

    plt.setp(line2, linewidth=10)

---

## __Set the line color__

### __set the line color for the selected line, here line__

    plt.setp(line1, color='m')

OR

    plt.setp(line1, color='#FFC000')

OR

    plt.setp(line1, color=(0, 0.7, 1))

<br />

### __set the line color for the selected line to grey, here line1__

    plt.setp(line1, color='0.5')

<br />

### __set the line color for the selected line(s) with mpl.colors.hsv_to_rgb, R/G/B values in % in the brackets__

    plt.setp(line1, color=mpl.colors.hsv_to_rgb((0.3, 1, 1)))

    plt.setp(line2, color=mpl.colors.hsv_to_rgb((0.3, 1, 0.6)))

---

## __Set the line style__

### __set the line style for the selected line__

    plt.setp(line2, linestyle='--')

<br />

### __set the stroke length or even define the shape of the stroke ends__

    plt.setp(line2, dashes=(4, 2), dash_capstyle='round')

<br />

### __.cla() for "clear current axes" deletes current plot__

    plt.cla()

---

## __Marker points__

### __Define marker points on a line__

If you have 2 different lines in a plot, you can select the color of the line and the format of the marker points in 1 bracket for each:

    plt.plot(x, y1, 'ro-')

    plt.plot(x, y2, 'yD-')

* Both lines have the same x axis, so there is 1 x only. But you need to define the y1 or y2 for each line.
* 'ro-' = r stands for the color RED, o stands for the symbol of the point (here a circle)
* 'yD-' = y stands for the color YELLOW, D stands for the symbol of a diamond

<br />

### __Change size of the marker points__

* Standard marker size is 6
        
        plt.getp(line1, 'markersize')

* Change the size

        plt.setp(line1, markersize=4)

        plt.setp(line2, markersize=10)

<br />

### __Marker points dictionary with further formats__

    mpl.lines.Line2D.markers

    Out: {'.': 'point', ',': 'pixel', 'o': 'circle', 'v': 'triangle_down',
    ...
    8: 'caretleftbase', 9: 'caretrightbase', 10: 'caretupbase',
    11: 'caretdownbase', 'None': 'nothing', None: 'nothing',
    ' ': 'nothing', '': 'nothing'}


![filled marker](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/matplotlib_filled_marker.png)

![unfilled marker](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/matplotlib_unfilled_marker.png)

---
---

# __Format the plot: axis__

### __Format the font size with 2 different possibilities__

    plt.xlabel('t', fontsize='x-large')

OR

    plt.ylabel('cos(t), sin(t)', fontsize=30)

<br />

### __Format the axis font if a greek letter or mathematical symbol is included (use $)__

    plt.xlabel('$t$')

    plt.ylabel(r'$\cos(\omega t), \sin(\omega t)$')
OR

    mpl.rc('text', usetex = True)

    plt.ylabel(r'$\cos(\omega t), \sin(\omega t)$')

<br />

### __Define the axis (start and end of the axis) - here start at 4 instead of 0 and ends at 6__
    
    plt.xlim(4, 6)

---
---

# __Format the plot: legend__

### __Add a label (after the marker format) to prepare the legend__

    plt.plot(x, y1, 'o-', label='Kosinus')

    plt.plot(x, y2, 's-', label='Sinus')

<br />

### __Show the legend (last step before plot show!)__

    plt.legend()

<br />

### __If you want to add the location of the legend use loc in round bracket__

    plt.legend(loc='upper right')

<br />

### __If the legend should be outside of the plot__

* legend is placed with the upper left corner slightly outside the upper right edge of the graphic
* exact point is specified relative to the so-called "bounding box", which has here always the horizontal and vertical length 1, thus is independent of the problem coordinates, which run here in horizontal direction from 0 to 10 and in vertical direction from -1 to 1.
* point (1.02, 1) thus lies as claimed slightly to the right of the upper right corner of the graphic 

        plt.legend(bbox_to_anchor=(1.02, 1), loc='upper left', borderaxespad=0)

---
---

# __Save the plot as a file__

* __graphic (.jpg/.png)__

        plt.savefig('example.png')


* __pdf file__

        plt.savefig('example.pdf')
