## The Basis of Cascading Style Sheet (CSS)
`CSS` is used to add styling(presentation) to an `HTML` document.

> CSS Declaration

The property name and value are separated by a colon, and the entire declaration must be terminated by a semi-colon.

```css
selector {
  css ruleset
  property-name : "value";
}
```
> Adding CSS to HTML Document
- Using the style tag (in the head tag)
  
  ```css
  <style>
    h1 {
        font-size: "16px";
      }
  </style>
  ```

- Using Inline css

```html
      <p 
        style="
          font-size: 1rem;
          background-color: purple; 
          padding: 1.5rem;
          border-radius: 10px;
        "
       >
        I am a paragraph tag
      <p>
```
  `<p 
      style="
        font-size: 1rem;
        background-color: purple; 
        padding: 1.5rem;
        border-radius: 10px;
      "
      >
       I am a paragraph tag
      <p>

- Using External css (recommended)
  
  `index.html`
  ```html
  <head>
    <link rel="stylesheet" href="./style.css" />
  </head>
    <body>
      <div>
         <h1>
             Lorem ipsum dolor 
             sit amet 
             consectetur 
             adipisicing 
          </h1>
          <p>
            hello paragraph
          </p>
      </div>
    </body>  
  ```
  `style.css`
  ```css
    h1 {
        font-size: "16px";
      }

    p {
        color: blue;
        background-color: black;
        padding: 5rem;
        border-radius: 2rem;
      }

  ```


## CSS Selector

- **Universal Selector (*)**
  
Adding general style to an `HTML` Elements

 ```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Courier New';
  }
  ```
- **Class Selector (`.class`)**
  
    `index.html`
  ```html
  <head>
    <link rel="stylesheet" href="./style.css" />
  </head>
    <body>
      <div class="container">
         <h1 class="title">
             Lorem ipsum dolor 
             sit amet 
             consectetur 
             adipisicing 
          </h1>
          <p class="description">
            hello dev, 
            I am a paragraph
          </p>
      </div>
    </body>  
  ```
  `style.css`
  
  ```css
  
  .container {
    color: blue;
    background-color: black;
    padding: 5rem;
    border-radius: 2rem;
  }

  .title{
    font-size: "16px";
    font-weight: 400;
  }
  .description{
    font-size: "16px";
    text-align: "center";
  }
  ```
- **Id Selector (``#id``)**


 ```css
  
  #container {
    color: blue;
    background-color: black;
    padding: 5rem;
    border-radius: 2rem;
  }
  ```

- **Element Element Selector(Grouping Selector with similar style) 
(e.g `p`, `h1`, `h2`, `h3`)**

 ```css
h1,
h2, 
h3, 
p {
    color: blue;
    font-weight: 700;
  }
  ```

- **Element Class Selector: select only the element with the specified class (`h1.class`)**

 ```css
  h1.container {
     color: blue;
     font-weight: 700;
  }
  ```

- **Styling Attributes (Applying styles to `HTML` Attributes) 
(e.g `href`)**

```html

    <a href="./about-us.html">About us</a>

```

```css
[href]{
  color: blue;
}
```
or using `href` with a `value`

```css
[href="#"]{
  color: blue;
}
[href="./about-us.html"]{
  color: blue;
}
```

- **Pseudo-Classes in CSS**
  
Pseudo-classes are selector types that allow you to select elements in a particular state.
Pseudo-classes uses single colon notation `:`

Examples are `:hover`, `:disabled`, `:required`, `:checked`, `:visited` e. t. c

```css
  button:hover{
    background-color: black;
    color: white;
  }
```

[Learn more on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

- **Pseudo-elements in CSS**
  
Pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s).
Double colons notation `::` are used for pseudo-elements that differentiate them from Pseudo-classes.

Examples are `::first-line`, `::first-letter`, `::placeholder`, `::after`, `::before` e. t. c

```css
selector::pseudo-element {
  property-name: value;
}
```

illustration

```css
::placeholder{
  color: red;
  font-size: 1rem;
}
```

```css
  /* The first line of every <p> element. */
p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

[Learn more on MDN on Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

 **CSS Combinators (Relationship between elements)**
 ----------------------------------------------------
   These allow the combination of multiple selectors
   to target specific elements in the DOM for styling.

   In other word, combinators allow developers to use multiple selector types. Based on the relationship between the elements in the DOM that match these selectors.
   
   The following are the available CSS Combinators

  > Descendant Combinator: 

  This combinator allows the selection of an element that is a descendant of another element. _Descendants_ can be child, grandchild, great-grandchild elements.

    

illustration

```html
      <p>I am the first p</p>

      <div class='container'>
         <p>I am the second p</p>
         <div>
          <p>I am the third p</p>
         </div>
      </div>

      <p>I am the last p</p>
 ```

To use this combinator, you enter an empty space between selectors like this:

```css

  .container p {
    color: rebeccapurple;
  }
```
This style declaration above selects p elements that are descendants of elements with the `.container`

From the result above, you can see the second and third `p` styled. This is because they are both descendants of the `.container` element. The second `p` is a `direct child` while the third `p` is `grandchild` (direct child of the div) but they are descendants.

To styled only the third p , the `CSS` ruleset becomes

```css

 .container div p {
    color: rebeccapurple;
  }
```

 > Child Combinator:

 The child combinator selects elements that are direct children of another element. 
 So You can use the greater than symbol `>` between selectors to specify that an element is a direct child of the other.



illustration

```html
      <p>I am the first p</p>

      <div class='container'>
         <p>I am the second p</p>
         <div>
          <p>I am the third p</p>
         </div>
      </div>

      <p>I am the last p</p>
 ```

To use child combinator, you can use the greater than symbol  `>`  between selectors like this:

```css

  .container > p {
    color: rebeccapurple;
  }
```
To style the child of a direct of class `container`, we do:

```css

  .container > div > p {
    color: red;
  }
```

> Sibling Combinator:

The sibling combinator used between selectors matches elements that are siblings of another element. This means that, it only style _ALL(siblings)_ elements that are _AFTER_ it and not elements that are _BEFORE_ it.

So to use Sibling combinator, you enter the tilde (~) symbol. 
Here is an illustration:

```css

  div ~ p {
    color: red;
  }
```
This styling selects all `p` elements that are siblings of `div` elements. That is all `p` elements that are _AFTER_ the `div`

illustration

```html
      <p>I am the first p</p>

      <div class='container'>
         <p>I am the second p</p>
         <div>
          <p>I am the third p</p>
         </div>
      </div>

      <p>I am the last p</p>
      <p>I am the very last p</p>
 ```
Only the last two `p` become red in color because they are siblings _AFTER_ to `div` element with the `class`  `container` .


> Adjacent Combinator:

The adjacent combinator matches only the _IMMEDIATE_ sibling that comes _AFTER_ an element.

So to use Sibling combinator, you use plus `+` symbol. 
Here is an illustration:

```css

  div + p {
    color: red;
  }
```


```html
      <p>I am the first p</p>

      <div class='container'>
         <p>I am the second p</p>
         <div>
          <p>I am the third p</p>
         </div>
      </div>

      <p>I am the last p</p>
      <p>I am the very last p</p>
 ```

 So only the fourth `p` is styled. This is because this `p` element is an **immediate sibling** after the `div` element in our HTML code.