# Understanding 2D and 3D Transforms 

Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane. Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the x and y axes, as well as the z axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth. We’ll start by discussing how to transform elements on a two-dimensional plane, and then work our way into three-dimensional transforms.

### Understanding values of Transform (Rotate, Scale, Translate)

1. Rotate: This value will rotate the figure element to a desired state. Keeping in mind that 2D tranform will only work on the x and y axes unlike 3D Transform which has an extra axes which z-axes.
2. Scale: This value will increase or decrease the size of a figure or object. This value also has children which are ScaleX and ScaleY which will only increase or decrease either the X-axes or Y-axes.
3. Translate: This value will move the figure element. Like the Scale sibling, this also has children which soley target the X=axes or the Y-axes.
4. Skew: This value will skew the figure element. In laymen term, this will move side-a south while moving side-b north. This can also get more complicated movements by moving a targeted side south-south-east as an example.
5. Cube: It is possible to make a 3d object like a cube using 
6. Origin: To change the default transform origin position, the transform-origin property is used and this accepts one or two values. When only one value is specified, that value is used for both the horizontal and vertical aces. If two values are specified, the girst is used for the horizontal axis and the second is used for the vertical axis.

 - Individually the values are treated like that of a background image position, using either a length or keyword value. That said, 0 0 is the same value as top left, and 100% 100% is the same value as bottom right. More specific values can also be set, for example 20px 50px would set the origin to 20 pixels across and 50 pixels down the element.

### Combining Transform

It is common for multiple transforms to be used at once, rotating and scaling the size of an element at the same time for example. In this event multiple transforms can be combined together. To combine transforms, list the transform values within the transform property one after the other without the use of commas. i.e. transform: rotate\(25deg\) scale(.75);

### Perspective

In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.