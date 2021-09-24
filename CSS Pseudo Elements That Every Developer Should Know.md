Pseudo-elements are used to select and apply the styles to the particular element or part of elements in the DOM.

![CSS Pseudo Elements That Every Developer Should Know](https://miro.medium.com/max/1276/0*q2jSpoF-a0sZMg0w.jpeg)

CSS Pseudo Elements That Every Developer Should Know

# What is Pseudo Element?

Pseudo-elements are used to select and apply the styles to the particular element or part of elements in the DOM.

Pseudo-elements denoted by ( **::** ) symbol.

Multiple Pseudo-elements can be used for a single element.

> *selector::pseudo-element {
> property: value;
> }*

**Example :**

Pseudo-elements help to apply the style to the first letter or first line of your HTML elements.

There are six types of Pseudo-elements let’s see each pseudo-element with an example.

# 1) ::first-line

The::first-line pseudo-element helps to select and apply the style to the first line of text and paragraph and heading.

The::first-line element we can only use these property font,color,background,word-spacing,letter-spacing,text-decoration,vertical-align,text-transform,line-height and clear.

**Note**::first-line pseudo-element works only on block-level elements.

**Example:**

> **HTML**
>
> **CSS**
>
> *p::first-line {
> color: green;
> }*

# 2) ::first-letter

The::first-letter pseudo-element helps to select and apply the style to the first letter of text and paragraph and heading.

The::first-line element we can only use these property font,color,background,margin,padding,border,text-decoration,vertical-align (only if “float” is “none”),text-transform,line-height,float and clear.

**Example:**

> **HTML**
>
> **CSS**
>
> *p::first-letter {
> color: red;*
>
> *font-size: 18px;
> }*

# 3) ::before

The::before pseudo-element helps to add or insert content to the before the content of an element.

**Example:**

> **HTML**
>
> **CSS**
>
> *p::before {
> content: url(smiley.gif);
> }*

# 4) ::after

The::after pseudo-element helps to add or insert content to the after the content of an element.

**Example:**

> **HTML**
>
> **CSS**
>
> *p::after {
> content: url(smiley.gif);
> }*

# 5) ::marker

The:: marker pseudo-element helps to apply the style to the order and un-order list.

**Example:**

> **HTML**
>
> *<ul>*
>
> *<li>Attractive Aurora</li>*
>
> *<li>Attractive</li>*
>
> *<li>Aurora</li>*
>
> *</ul>*
>
> **CSS**
>
> *::marker { 
> color: red;
> }*

# 6) ::selection

The:: selection pseudo-element helps to apply the style to the user-selected text.

The::selection pseudo-element accepts the minimum number of CSS properties.

The ::selection pseudo-element supports colors,background,outline and cursor.

**Example:**

> **HTML**
>
> **CSS**
>
> *::selection {
> color: red; 
> background: yellow;
> }*

**I think this information is helpful to you.**

**Thanks for reading — Don’t Forgot To Share & Comment**

Any suggestion or queries please comment, our team will response asps.