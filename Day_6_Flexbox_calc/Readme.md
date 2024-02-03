# CSS Flexbox

### Whats is Flexbox ?
Flexbox is a way to layout elements in CSS and is broken into a two main components. The flexbox container and flexbox items. The flexbox container is the parent element that contains all the flexbox items as its children. The flexbox container is where you define all your properties about the flexbox layout and then on the individual items you can make additional tweaks. Let’s take a look at how we would get started with a simple flexbox example. If we have an element with children inside of it all we need to do is set the display property of the parent element to flex and we will have a flex container. display: flex
![](../img/flexbox.png)

### Flexbox layout

Flexbox was the first CSS layout method that worked in a completely different way than normal CSS. Instead of worrying about block/inline elements flexbox worries about a main axis and a cross axis.

#### justify-content
```css
.flex-item{
    width: 20%;
}
```
#### flex-start
Places all items at the start of the main axis which is the left side of the axis by default. This is also the default behavior of justify-content.
```css
.flex-container{
    display:flex;
    justify-content:flex-start;
}
```
![](../img/flexbox.png)

#### flex-end
places all items at the end of the main axis which is the right side of axis by default.

```css
.flex-container{
    display: flex;
    justify-content: flex-end;
}
```
![](../img/flex-end.png)

#### center
Places all items in the center of the main axis. This is one of the easiest ways to center elements in CSS.

```css
.flex-container {
  display: flex;
  justify-content: center;
}
```
![](../img/flex-center.png)

#### Space between
This takes all the extra space insdie the container and evenly spreads it betwwen each element to space them as far apart as possible from one another while filling the full container.

```css
.flex-container {
  display: flex;
  justify-content: space-between;
}
```
![](../img/flex-space-between.png)

### Space-around
This is very similar to space-between, but it also adds space between the outside of the container and the first/last element. The amount of space between the outside of the container and first/last element is exactly half the amount of space between elements 

```css
.flex-container {
  display: flex;
  justify-content: space-around;
}
```
![](../img/flex-space-around.png)

#### space-evenly
This is very similar to space-around, but the space between the outside of the container and the first/last element is the same as the space between elements instead of half the size.

```css
.flex-container {
  display: flex;
  justify-content: space-evenly;
}
```
![](../img/flex-space-evenly.png)

#### align-iteams 
For all these examples we will assume that the flex-items all have a width of 20%, but that the elements are all different heights.

```css
.flex-item {
  width: 20%;
}

.flex-item:nth-child(1) {
  height: 75px;
}

.flex-item:nth-child(2) {
  height: 100px;
}

.flex-item:nth-child(3) {
  height: 125px;
}
```
#### stretch (default)
This will stretch all items to fill the full height of the cross axis unless they have a specific height set. In our example I set the height of the first child to initial which is essentially the same as if we had never set a height on the first child. By default when a div has no height it will just be the height of the content inside of it, but as you can see below the first child fills the full height of the container since it is stretching to fill the full height. The second element is not stretching, though, since we set a specific height of 100px on it. This is the default behavior of align-items.

```css
.flex-container {
  display: flex;
  align-items: stretch;
}

.flex-item:nth-child(1) {
  /* This is the same as if we had not set a height */
  height: initial;
}
```
![](../img/flex-stretch.png)

#### flex-start
This works the same as flex-start for justufy-content, but will start at the top os the cross axis by default.
```css
.flex-container{
    display: flex;
    align-iteams: flex-start;
}
```
![](../img/flex-start.png)

#### flex-end
This works same as flex-end for justify-content, but will start at the bottom of the cross axis by default

```css
.flex-container {
  display: flex;
  align-items: flex-end;
}
```
![](../img/flex-end(1).png)

### center
this works same as center for justify-content, but will be center based on the cross axis

```css
.flex-container {
  display: flex;
  align-items: center;
}
```
![](../img/flex-center(1).png)

Now this covers all the ways you can layout elements along the main and cross axis, but there is one more important thing you need to know about flexbox axes. They can actually be swapped. There is a property called flex-direction which determines the orientation of the main and cross axis.

#### flex-direction
This property allows us to determine which direction each axis corresponds to as well as where the axis start

####
row(default)
The default direction is row. This means the main axis is horizontal while the cross axis is vertical. This also means the main axis starts on the left while the cross axis starts at the top.

```css
.flex-container{
    display:flex;
    flex-direction: row;
    justify-content: flex-start;
    align-iteams: flex-start;
}
```
![](../img/row.png)

Similar to row we have row-reverse. This direction does not swap the main/cross axis, but it does swap where the main axis starts. The main axis now starts on the right while the cross axis does not change and still starts at the top. You will see below that our items start on the right side of the container and are ordered right to left since we are using the reverse ordering

```css
.flex-container {
  display: flex;
  flex-direction: row-reverse;
  justify-content: flex-start;
  align-items: flex-start;
}
```
#### Column
The column direction completely swaps our axes so now the main axis is vertical and the cross axis is horizontal. This means that if you use justify-content you will be laying out elements in the vertical direction and align-items will work in the horizontal direction.

```css

.flex-container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

```
![](../img/column.png)

# CSS Calc
First, we need to talk about what CSS calc is and how you use it. In the simplest terms possible CSS calc is just a CSS function, similar to rgb, var, etc. that lets you do addition, subtraction, division, and multiplication on various CSS units. Here is a simple example.

```css
.class{
    width: calc(200px + 100px);
}
```

### Combining Different Units
That’s right. With CSS calc we can combine together different CSS units to create values that are impossible to represent with traditional CSS units. For example what if we wanted to create a box that was 30px away from being 100vw wide. Essentially a 100vw box that had 30px of space removed from it.

```css
.class{
    width: calc(100vw - 30px);
}
```
That’s all you need to do. Just put the 100vw and the 30px into your calc function and CSS will take care of all the complex math for you. Now no matter how wide or small your screen is the box will always be 30px smaller than the full width of the screen.

Now this alone is enough to make CSS calc amazing, but you can go a step further and combine this with CSS variables.

### CSS variables And Calc
Now with that out of the way can talk about how you can use CSS variable with calc. All you need to do is replace on of your values in the calc function with variable
```css
.class{
    --w: 100px;
    width: calc(var(--w) *2);
}
```
We now have a box that is 200px wide since we are multiplying the 100px --w variable by 2.