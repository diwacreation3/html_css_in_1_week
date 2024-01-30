# CSS Selector
To start we need to cover the most basic form of selectors and also talk about what a CSS selector is. A CSS selector is simply the code you write that determines which HTML elements your CSS styles will refer to. In the below example .class-name is the CSS selector since it is the part that comes before the curly braces.
```css
.class-name{
    color:blue;
}
```

### Universal Selector
The universal selector, Which is just a *, does lke it's name says and selects everything. The below code would set the mirgin to 0 on all element on the page. 
```css
*{
    margin:0;
}
``` 
This selector is perfect for when we want to make large changes accross our entire page such as setting box-sizing or removing margins, but is generally bot used for much else.

### Type Selector
The type selector is selector that we will use relatively rarely as it is just too general to be useful. The type selector allows you to select all elements of a particular type, such as all div or img elements. To use this selector just put the name of the element you want to select. The Below example selects all div elements 
```css
div{
    background-color: royalblue;
}
```
I recommend never using this type os selector it is too easy to acce\identally add styles to elements you don't actually want to a style too. The only time i would ever use the type selector is if I wanted to set some default styles that apply to my entire site such as setting font-size for heading tags, or selecting the body tag to remove margins.

### Class selector
 This is by far the most common type of selector that you will see. Classes are attributes that you can add to any html element that serve no purpose other than to be used with CSS or javascript. these class selectors are amazing in CSS since they allow you to specify ehich elements you want style in the html
 ```html
 <button class="btn btn-primary"> save </button>
 <button class="btn btn-danger"> Cancel </button>
 ```
 In the above example you can see we gave both our buttons the btn class so they can both share the styles associated with that class in our CSS. We also gave them each their own btn-primary or btn-danger class to add extra styles for those specific buttons. To use a class selector in CSS you simply put the name of the class you want to select after a period.
 ```css
 .btn{
    border: 1px solid black;
 }

 .btn-primary{
    background-color: blue;
 }
 .btn-danger{
    background-color: red;
 }
 ```

### Id Selector

The final basic selector is id selector. They are very similar to class selectors in that we can define ids on HTML elements and then reference them in CSS but there are a few differences.
The first main difference is that id selector cannot be shared between elements on the same page since in html and id is unique so no two elements on the page can have the same id. \

ID selectors are also more specific which makes them overide a lot of other CSS styles which you do not want. is you are unsure of how specificity works in CSS. \
The final difference is the id selector with # symbl insted of a period.
```html
<nav id="nav-bar">...</nav>
```
```css
#nav-bar {
  margin-bottom: 1rem;
}
```
### Combination Selector
The real power of CSS selector comes in your ability to combine selector you need to know which will allow you to select the exact element you want every time. \

### Descendant Selector
The first type of combination selector is the descendant selector is the descendant selector. This selector allows you to select any element that matches a specific selector ehich is a descendant of an elemant that matches a different selector.
```css
div span{
    color: blue;
}
```
```html
<div>
    <span> Selected </span>
    <a>
        <span> Selected </span>
    </a>
</div> 
<span> Not </span>       
```
The above CSS selector selects all span elements that are descents of a div element. You will notice that this means the first span is selected since it is a direct child of the div.

### Direct Child Selector

Similar to the descendant selector, the direct child selector is for selecting child elements, but the main difference is the direct child selector will only select an element that is the direct child of the first parent selector.
```css
div > span{
    color:blue;
}
```
```html
<div>
    <span> Selected </span>
    <a>
        <span> Not </span>
     </a>
     </div>
     <span> Not </span>   
```
As you can see above the span inside the a tag is not selected since it is not a direct child of the div and instead is a direct child of an a tag. The first span is selected, though, since it is the direct child of a div.

### General Sibling Selector 
This next selector is all about selecting siblings, but can be a bit confusing. lets take a look at an example 
```css
div ~ a{
    color: blue;
}
``` 
```html
<a> Not </a>
<div> </div>
<a> Selected </a>
<a> Selected </a>
```
You would think since this selector is called the general sibling selector that it would select all elements that are siblings of the first element, but it actually only selects the siblings that come after the first selector. This is because CSS can only read in one direction so has no way to modify elements that come before other elements.

As for the actual selector itself all you need to do is put a ~ between the selectors. The first selector will be for the sibling to check after and the second selector is for the actual siblings you are checking for.

### OR Selector
Now we are coming to my two favorite combination selectors,the or and and selectors. First we will talk about the or selector which is a way to write a CSS selector that will select elements that match at least one of the selectors.
```css
div, span {
    color: blue;
}
```
```html
<div> Selected </div>
<a>  Not </a>
<div> Selected </div>
<span> Selected </span>
```
The above selector selects all elements that are either a div or a span. This is great if you want to have multiple selectors do the same thing. To use the or selector just separate your selectors by a comma. Generally, if the selectors are long I will separate them onto different lines to make them easier to read.

```css
.really-really-long-time,
.anothe-name{
    color: red;
}
```
### And Selector
The final combination selector is the and selector and it is probably the most used conbination selector. This Selector allows you to write CSS Selector that force elements to match all the selectors specified 
```css
div.blue {
    color: blue;
}
```
```html
<div class="blue"> Selected </div>
<div> Not </div>
<span class = "blue"> Not </span>
```
As you can see only the div with the class of red is selected in the above example. Using the and combination selector is also incredibly easy since all you have to do is write all the selectors right next to each other with no spacing between them.

The only important thing to know about this selector is that if you are using a universal selector or a type selector then you must put the type/universal selector first.

```css
div.blue{
    
}  /* Good*/

.reddiv{

}/* bad*/
```

## Pseudo Element Selectors 
Now that we have covered the most common types of selectors we need to talk about a few other selectors that you will still use all the time, but are a bit more niche. The first type we are talking about are pseudo element selectors which there are only 2 that you need to know and they are both almost

```css
div::before{
    content: "child 0";
}
```
```html
<div>
    <span> Child 1 </span>
    <span> Child 2 </span>
</div>    

```
In the above code we are using the before pseudo selector to select the before element for our div. This will create a new element in our HTML that has the text “Child 0” inside of it. You will notice in our HTML, though, there is no element corresponding to the ::before element and that is because the pseudo element is created entirely in CSS and when we write our HTML we don’t reference it.

Now to create a pseudo element just prefix it :: and then put the type of pseudo element you are selecting. In our case we are creating a before pseudo element inside every div on our page.

### After Pseudo Element 
The after pseudo element is exactly the same as the before pseudo element expect that it is added as the last child of the element insted of the first.

```css
div::after{
    content: "child 3"
}
```
```html
<div>
    <span> Child 1 </span>
    <span> Chid 2 </span>
</div>    
```

### Pseudo Element Selector Important Notes

You must include a content property for your pseudo elements or they will not exist on the page. it can simply be an empty be empty string, through. if you don't want it to have any content.

```css
div::after{
    content: "";
}
```
pseudo elemets also can be defined using a single colon, but this is not recommended and is only implemented for backwards compatibility.
```css
div:after{
    content: "Technically it works";
}
```
You also cannot add pseudo elements to elements that replace their content with something else such as an img element.

Lastly, pseudo elements will show up in your browser dev tools which can make debugging them much easier.

### Pseudo Class Selector 
Now this is really where CSS starts to become a vast world of selectors. There are hundreds of pseudo classes which are all used to represent special states of elements that you can use as selectors in CSS, but there are really only a handful that are truly important for you to understand.

### Hover pseudo Class
probably the most useful CSS pseudo class is hover. The hover pseudo class allows you to style an element differently when it is hovered. for example, you can chage the background color of a button so users know it is clickable.
```css

button:hover{
    background-color: blue;
}
```
###  Focus pseudo Class
the focus pseudo class is another really important selector since it allows you to style an element based on if it has focus or not. for example you can change the border color of an input field when it is focused.
```css
input:focus{
    border-color: blue;
}
```
### Checked pseudo Class
The checked pseudo class allows you to style an element based on if it is checked or not. For example you can change the opacity of a checkbox when it is checked.
```css
input:checked {
  opacity: 0.8;
}
```