 Specificity
-------------

If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element.

Specificity Hierarchy
---------------------
Every CSS selector has its place in the specificity hierarchy.
There are four categories which define the specificity level of a selector:

1. Inline styles 

  Example: `<h1 style="color: pink;">`
  
2. IDs - Example: #id

3. Classes, pseudo-classes, attribute selectors - Example: `.test`, `:hover`, `:active`, `:focus`, `[href]`

3. Elements and pseudo-elements
   
  Example: `h1`, `::before` `::after`

Examples
--------
- Using element selector
- Using class selector
- Using id selector
- Using inline style(highest priority)
  
Note: There is one exception to this rule: if you use the !important rule, it will even override inline styles!

How to use !important rule
--------------------------
The `!important` rule in CSS is used to add more importance to a property/value than normal.
In fact, if you use the !important rule, it will override ALL previous styling rules for that specific property on that element!



