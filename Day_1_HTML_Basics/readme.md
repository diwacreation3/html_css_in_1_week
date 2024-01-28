# HTML Basics 

### HTML Documents 
All HTML documents must start with a document type declaration ```<!DOCTYPE html> ``` \ 
The HTML document itself begins with ```<html>``` and ends with ```</html>``` \
The visible part of the HTML document is between ```<body>``` and ```</body>```

#### Example 
```html
<!DOCTYPE html>
<html>
    <body>
        <h1> Hello Nepal </h1>
        <p> Buddha was born in nepal </p>
    </body>
    </html>
```
### HTML Headings 
HTML headings are defined with the < h1> to < h6> tags. < h1> defines the most important heading. < h6> defines the least important heading

#### Example
```html
    <h1>Hello Nepal</h1>
    <h2>hello Buddha</h2>
    <h3>hello Buddha</h3>
    <h4>hello Buddha</h4>
    <h5>hello Buddha</h5>
    <h6>hello buddha</h6>
```

### HTML Paragraphs
 HTML paragraphs are defined with < p> tag:
```html
<p> Buddha was born in nepal </p>
<p> you will find heavenly places in nepal </p>
```
### HTML Links
HTML Links are defined with the < a> tag: 
```html
<a href="https://diwakar-phuyal.com.np"> This is link </a>
```
The link destination is specified in the href attribute. \
Attributes are used to provide additional information about HTML elements.

### HTML Images 
HTML images are defined with the < img> tag. \
The source file ( src ), alternative text ( alt ), width and height are provided as attributes:
```html
<img src="/img/buddha.jpg" alt= "Buddha" width = "100" height = "120">
```

### HTML Formatting Elements 
Formatting elements were designed to display special types of text:

- < b> - Bold Text
- < strong> - Important Text
- < i> - Italic text
- < em> - Emphasized text
- < mark> - Marked text
- < small> - Smaller text
- < del> - Deleted text
- < ins> - Inserted text
- < sub> - Subscript text
- < sup> - superscript text

```html
<b> This text is bold </b>
<strong> This text is important</strong>
<i> This text is italic </i>
<em> This text is emphasized </em>
<small> This is some smaller text </small>

<p> Don't forget to buy  <mark> Milk </mark> today. </p>

<p> My favorite color is <del> blue </del> green </p>

<p> My favorite color is <del> blue </del>  <ins>green</ins> </p>

<p> this is <sub> subscripted </sub> text. eg H<sub>2</sub>O </p>

<p> this is <sup> superscripted</sup> text. eg O<sup>3</sup> </p>

```
### HTML Lists
HTML lists allow web developers to group a set of related items in lists.

#### Unordered HTML Lists 
An unordered list starts with the < ul> tag. Each list item starts with the < li> tag.
```html
<ul>
    <li> MOMO </li>
    <li> paniPuri </li>
    <li> Chatpatey </li>
 </ul>   
```
#### Ordered HTML List
An unordered list starts with the < ul> tag. Each list item starts with the < li> tag.

```html
<ol>
    <li> MOMO </li>
    <li> paniPuri </li>
    <li> Chatpatey </li>
 </ol>   
```
#### HTML Description Lists
HTML also supports description lists.

A description list is a list of terms, with a description of each term.

The < dl> tag defines the description list, the < dt> tag defines the term (name), and the < dd> tag describes each term:
```html
<dl>
    <dt> MOMO </dt>
     <dd> - Steam hot </dd>
     <dt> Panipuri </dt>
     <dd> - with lots of pani(masala water)
  </dl>      
```
