# CSS Custom properties 
As i already mentioned custom properties are a way to declare variable
in css. here is a simple example of s CSS custom property.
```css
body{
    --custom-property: 10px;
}

```
As you can see, defining custom properties ia pretty much that same as defining any otner property in CSS, with the only real difference being that custom properties must start with two hypens --.
you can use nay text after two hypens that you want and taht will be the name os custom property you are creating. Thean all that is left to do is give the property a value just like any other CSS property. Using thsese properties is also incredibly straightforward. CSS has a var function ehivh takes the name of a property and outputs the value of that property.

```css
body{
    --primary-color: #0af;
    background-color: var(--primary-color);
}
```
The only important things to remember is that two hyphens in the custom property name must be invlude in the var function ot the variable will not work. Now that is all the code it takes to create the most simple custom property, but custom properties can do so much more than just contain a simple variable in a single selector.

## Custom properties In the cascade 
Just like everything else in CSS, custom properties can be overwritten based on where they fall in the CSS cascade. To start, custom properties always inherit into child elements. This means that if a custom property is defined in the body or root element, then it will be available in all child elements.
```css
body{
    --button-color: red;

}
button{
     /* All buttons will be red */
  background-color: var(--button-color);
}
```

When a custom property is defined multiple times in a stylesheet the most specific value based on the normal CSS cascade will be used.

```css
.btn {
  /* Any elements with the class .btn will be red */
  --button-color: red;
  background-color: var(--button-color);
}

.btn.btn-primary {
  /*
    Any elements with the classes .btn and .btn-primary
    will be green since the --button-color custom property
    is being overwritten with the green value
  */
  --button-color: green;
}
```
Because of the similarities between these two sets of code you may wonder why even use custom properties. In my opinion, the biggest benefit to using custom properties in this way is when you want to overwrite single parts of a property without redefining the entire property.

```css
.btn-hover{
    --scale: 1;

    transform: rotate(45deg) scale(var(--scale));
}

.btn.btn-grow:hover{
    --scale: 1.5;
}
```
The eqlivalent of the above code would be this

```css

.btn:hover {
  transform: rotate(45deg);
}

.btn.btn-grow:hover {
  transform: rotate(45deg) scale(1.5);
}
```