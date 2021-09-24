# CSS Pseudo-Selectors You Might Have Missed

## Useful CSS pseudo-selectors that are often overlooked.

![img](https://miro.medium.com/max/2000/1*jrpPfGEYlAZlB5aRNMt2dA.jpeg)

> *(Pseudo) selectors let you assign styles to what are, in effect, phantom classes that are inferred by the state of certain elements, or markup patterns within the document, or even by the state of the document itself.*
>
> *— CSS: The Definitive Guide: Eric Meyer, Estelle Weyl*

This post is a sort-of encouragement to use more plain CSS and less JS when building your UI. Getting familiar with everything CSS has to offer is one way to achieving that — another one is implementing best practices and reusing that code, as much as possible.

Pseudo-Selectors are in categories: Pseudo-Classes and Pseudo-Elements.

Pseudo-Class acts as if a class has been attached to an element and styles the element on that basis, whereas a Pseudo-Element acts as if an element has been injected into another element and just the injected element is styled.

Pseudo-Classes has double colons :: while Pseudo-Elements has a single colon :.

To reuse your UI components try using cloud component hubs like [**Bit.dev**](https://bit.dev/). Use it to publish, document and organize all your team’s reusable UI components. It’s not only a way to build faster but also a way to build better as it encourages you to standardize and modularize your code.

[![img](https://miro.medium.com/max/1400/1*Nj2EzGOskF51B5AKuR-szw.gif)](https://bit.dev/)

Exploring shared UI components on [bit.dev](https://bit.dev/)

# ::first-line | Selects the first line of text

This pseudo selector affects the first line of text before a line breaks. It styles just the first line of text inside it, as if an element was wrapped around just that text.

```
p:first-line {
    color: lightcoral;
}
```

# ::first-letter | Selects the first letter

This pseudo selector applies to the first letter of the text in an element.

```
.innerDiv p:first-letter {
    color: lightcoral;
    font-size: 40px
}
```

# `::selection | Selects t`he highlighted (selected) area

This applies to any area that has been highlighted by the user.

With the `::selection` pseudo-selector, we can apply our styling to the area that we highlight.

```
div::selection {
    background: yellow;
}
```

# `:root | `Basic element

The `:root` pseudo-class selects the root element of the document. In HTML, it is always the HTML element. In RSS, it is the RSS element.

This pseudo selector is most used to store global rule values using CSS variable as it applies to the root element.

# `:empty | `Applies only if the item is empty

This pseudo selector will select any element that has no children of any kind. The element must be empty. An element is empty if it has no whitespace, visible content, or descendant elements.

```
div:empty {
    border: 2px solid orange;
}<div></div>
<div></div>
<div>
</div>
```

The rule will apply to empty div elements. The rule will be applied to the first and second div because they are truly empty, not the third div because it has whitespace.

# `:only-child | `Selects an only child

This applies to an element that is the only child of its parent element.

```
.innerDiv p:only-child {
    color: orangered;
}
```

# `:first-of-type | Selects the `first child element of a specified type

```
p:first-of-type {
    color: orangered;
}
```

This will select any paragraph which is the first paragraph inside another element, as if a class had been added to the paragraph itself.

```
.innerDiv p:first-of-type {
    color: orangered;
}
```

This would apply to the first child of `.innerDiv` of `p` paragraph element.

```
<div class="innerDiv">
    <div>Div1</div>
    <p>These are the necessary steps</p>
    <p>hiya</p>
    
    <p>
        Do <em>not</em> push the brake at the same time as the accelerator.
    </p>
    <div>Div2</div>
</div>
```

The p `("These are the necessary step")` would be selected.

# `:last-of-type | Selects the l`ast child element of a specified type

Same as `:first-of-type`, but this will affect the last child element of the same type.

```
.innerDiv p:last-of-type {
    color: orangered;
}
```

This would apply to the last child of `innerDiv` of type `p` paragraph element.

```
<div class="innerDiv">
    <p>These are the necessary steps</p>
    <p>hiya</p>
    <div>Div1</div>
    <p>
        Do the same.
    </p>
    <div>Div2</div>
</div>
```

So, the `p` element `("Do the same")` would be selected.

# `:nth-of-type() | `Selects the child element of a specified type

This selector would select an element of a certain type from the list of the specified parent element.

```
.innerDiv p:nth-of-type(1) {
    color: orangered;
}
```

# `:nth-last-of-type() | `Selects the child element of a type by the end of a list

This will select the last child element of a certain type.

```
.innerDiv p:nth-last-of-type() {
    color: orangered;
}
```

This will select the last child element in the list contained in the `innerDiv`element and of type, paragraph element.

```
<div class="innerDiv">
    <p>These are the necessary steps</p>
    <p>hiya</p>
    <div>Div1</div>
    <p>
        Do the same.
    </p>
    <div>Div2</div>
</div>
```

The p `Do the same` is the last paragraph child element inside the `innerDiv`so it will be selected and affected by the CSS rule.

# `:link | Selects an unvisited `hyperlink

This selector applies to links that have not been visited. This is mostly used with the `a` anchor element with href attribute.

```
a:link {
    color: orangered;
}<a href="/login">Login<a>
```

This will make all `a` anchor elements with a href attribute that has not been clicked to visit the page in its href attribute to have an orangered color text.

# `:checked | `Selects a checked checkbox

This applies to checkbox that has been checked.

```
input:checked {
    border: 2px solid lightcoral;
}
```

This rule applies to all checkboxes that have been clicked on to check it.

# `:valid | Selects an `element that is valid

This is mostly used in forms to visualize form elements that pass validation set by the user. When a validation passes, the defaulting element is set with the `valid` attribute.

```
input:valid {
    boder-color: lightsalmon;
}
```

# `:invalid | Selects a`n element that is invalid

Same as `:valid` but this will apply to elements that have failed the validation test.

```
input[type="text"]:invalid {
    border-color: red;
}
```

# `:lang() | Selects an element by a specified lang value`

This applies to elements that have their language specified.

It can be set in two ways either by this:

```
p:lang(fr) {
    background: yellow;
}
```

or

```
p[lang|="fr"] {
    background: yellow;
}<p lang="fr">Paragraph 1</p>
```

# `:not() | `Negates the following selections (this is an operator)

A negation pseudo-selector selects what is not.

Let’s see an example:

```
.innerDiv :not(p) {
    color: lightcoral;
}<div class="innerDiv">
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
    <div>Div 1</div>
    <p>Paragraph 3</p>
    <div>Div 2</div>
</div>
```

`Div 1` and `Div 2` will be selected because they are not `p` elements.

# Conclusion

That’s it. We exhausted the list. There are more pseudoselectors, but they are not standard so I left them out.

Thanks!!