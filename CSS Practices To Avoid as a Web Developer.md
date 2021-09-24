# CSS Practices To Avoid as a Web Developer

## Some bad habits and how to fix them…

Some people think that *CSS* is difficult to learn. There are lots of crutches and even some magic, which makes it easy to shoot yourself in the foot. I feel sad about this since I don’t think so.

After some research about what can we done, I’ve come up with **five developer habits** that I don’t like and will show you how to avoid them...

![img](https://miro.medium.com/max/700/1*CE96HtlZzAZJTLDCXIAdIw.png)

​																								CSS Practice to Avoid as a Web Developer

# 1. Set Margins or Padding and Then Reset Them

I often see people set margins or padding for all elements and then reset them for the first or last element. I don’t know why they use in there coding's. there’re two rules so that you can avoid them.

> Use one of the following for simpler and more concise CSS: `nth-child`/`nth-of-type`selectors, the `:not()` pseudo-class, or the adjacent sibling combinator better known as `+`.
>
> **Don’t do this:**

```
.item {
  margin-right: 1.6rem;
}

.item:last-child {
  margin-right: 0;
}
```

> **You can use:**

```
.item:not(:last-child) {
  margin-right: 1.6rem;
}
```

# 2. Add display: block for Elements With position: absolute or position: fixed

Did you know that you don’t need to add `display: block` for elements with `position: absolute` or `position: fixed` since it happens by default?

Also, if you use `inline-*` values, they will change as follows: `inline` or `inline-block` will change to `block`, `inline-flex` -> `flex`, `inline-grid` -> `grid`, and `inline-table` -> `table`.

> So, just write `position: absolute` or `position: fixed` and add `display` only when you need `flex` or `grid` values.
>
> **Do not do this:**

```
.button::before {
  content: "";
  position: absolute;
  display: block;
}
```

> **Or:**

```
.button::before {
  content: "";
  position: fixed;
  display: block;
}
```

> **You can use:**

```
.button::before {
  content: "";
  position: absolute;
}
```

> **Or:**

```
.button::before {
  content: "";
  position: fixed;
}
```

# 3. Use transform: translate (-50%, -50%) To Center

There was a popular problem that used to cause a lot of trouble. I’m talking about centering an element with an arbitrary height along two axes.

> one solution was to use a combination of absolute positioning and the `transform`property. This technique caused blurry text issues in Chromium-based browsers.

But after the introduction of flexbox, this technique, in my opinion, is no longer relevant. The thing is that it cannot solve the problem of blurry text. What’s more, it makes you use five properties. So, I would like to share a trick that can reduce the code to two properties.

> We can use `margin: auto` inside a `flex` container and the browser will center the element. Just two properties and that’s it.
>
> **Do not do this:**

```
.parent {
  position: relative;
}

.child {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

> **You can use:**

```
.parent {
  display: flex;
}

.child {
  margin: auto;
}
```

# 4. Use width: 100% for Block Elements

We often use flexbox to create a multi-column grid that gradually converts to a single column.

And to convert the grid to one column, developers use `width: 100%`. I don’t understand why they do it. The **grid elements are block elements** that can do this by default without using additional properties.

> So we don’t need to use `width: 100%`, but rather we should write the media query so that **flexbox is only used to create a multi-column grid.**
>
> **Do not do this:**

```
<div class="parent">
  <div class="child">Item 1</div>
  <div class="child">Item 2</div>
  <div class="child">Item 3</div>
  <div class="child">Item 4</div>
</div>.parent {
  display: flex;
  flex-wrap: wrap;
}

.child {
  width: 100%;
}

@media (min-width: 1024px) {
  .child {
    width: 25%;
  }
}
```

> **You can use:**

```
<div class="parent">
  <div class="child">Item 1</div>
  <div class="child">Item 2</div>
  <div class="child">Item 3</div>
  <div class="child">Item 4</div>
</div>@media (min-width: 1024px) {
  .parent {
    display: flex;
    flex-wrap: wrap;
  }

  .child {
    width: 25%;
  }
}
```

# 5. Set display: block for Flex Items

> When using flexbox, it is important to remember that when you create a flex container (add `display: flex`), all children (`flex` items) become blockified.

This means that the elements are set to `display` and can only have block values. Accordingly, if you set `inline` or `inline-block`, it will change to `block`, `inline-flex` -> `flex`, `inline-grid` -> `grid`, and `inline-table` -> `table`.

> So, don’t add `display: block` to `flex` items. The browser will do it for you.
>
> **Do not do this:**

```
.parent {
  display: flex;
}

.child {
  display: block;
}
```

> **You can use:**

```
.parent {
  display: flex;
}
```

# Conclusion

I hope I’ve managed to show you how to avoid simple mistakes and you will take my advice. Don’t foregate to clap for 15–20 times …

> Thanks for reading!