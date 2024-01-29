# HTML Advance Elements 
> i havent cover all the latest element 
### HTML DIV Element
The < div> elements is by default a block element, meaning that it takes all available width, and comes with line break before and after.
```html
Buddha was <div> Born in nepal </div>. Its Fact

```

### HTML tables
HTML Tables allow web developer to arrange data into rows and columns.
```html
<table>
  <tr>
    <th>Company</th>
    <th>Contact</th>
    <th>Country</th>
  </tr>
  <tr>
    <td>Leaf frog</td>
    <td>Ashish shrest</td>
    <td>Kathmandu</td>
  </tr>
  <tr>
    <td>Stupa Sphere</td>
    <td>Diwakar Phuyal</td>
    <td>Hetauda</td>
  </tr>
</table>

```
### HTML Class Attribute
The class attribute is often used to point to a class name in a style sheet. It can also be used by a JavaScript to access and manipulate elements with the specific class name.

In the following example we have three < div> elements with a class attribute with the value of "city". All of the three < div> elements will be styled equally according to the .city style definition in the head section:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.city {
  background-color: tomato;
  color: white;
  border: 2px solid black;
  margin: 20px;
  padding: 20px;
}
</style>
</head>
<body>

<div class="city">
  <h2>Kathmandu</h2>
  <p>Kathmandu is the capital of nepal</p>
</div>

<div class="city">
  <h2>Paris</h2>
  <p>Paris is the capital of France.</p>
</div>

<div class="city">
  <h2>Tokyo</h2>
  <p>Tokyo is the capital of Japan.</p>
</div>

</body>
</html>
```
### HTML id attribute
The id attribute specifies a unique id for an HTML element. The value of the id attribute must be unique within the HTML document.
The id attribute is used to point to a specific style declaration in a style sheet. It is also used by JavaScript to access and manipulate the element with the specific id.

The syntax for id is: write a hash character (#), followed by an id name. Then, define the CSS properties within curly braces {}.
In the following example we have an < h1> element that points to the id name "myHeader". This < h1> element will be styled according to the #myHeader style definition in the head section:

```html
<!DOCTYPE html>
<html>
<head>
<style>
#myHeader {
  background-color: lightblue;
  color: black;
  padding: 40px;
  text-align: center;
}
</style>
</head>
<body>

<h1 id="myHeader">My Header</h1>

</body>
</html>
```

### HTML Forms

An HTML form is used to collect user input. The user input is most often sent to a server for processing 

#### The < form> Element
The HTML < form> element is used to create an HTML form for user 
```html
<form>

</form>  
```
#### The < input> Element
The HTML < input> element is the most used form element.
An < input> element can be displayed in many ways, depending on the type attribute.

- < input type= "text"> \
Displays a single-line text input field

- < input type="radio"> \
Displays a radio button (for selecting one of many choices)

- < input type="checkbox"> \
Displays a checkbox (for selecting zero or more of many choices)

- < input type="submit"> \
Displays a submit button (for submitting the form)

- < input type="button"> \
Displays a clickable button

```html
<form>
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname">
</form>
```
### The label Element
Notice the use of the < label> element in the example above.
The < label> tag defines a label for many form elements.
The < label> element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focuses on the input element.

The < label> element also helps users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the < label> element, it toggles the radio button/checkbox.
The for attribute of the < label> tag should be equal to the id attribute of the < input> element to bind them together.