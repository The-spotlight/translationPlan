When it’s time to design websites, CSS Grid is useful for designing web pages. The difference between CSS Grid Layout and CSS Flexbox Layout is that Flexbow helps to create one dimensional layouts in columns and rows while Grid works in two dimensions to create lays in columns and rows simultaneously. Both of these features are similar in many regards, and after you learn one, it is easy to grasp the other. In this topic, I’m not going to discuss Flexbox because I want to explain about basics of Grid.

**Grid-template-columns:**

When setting display to Grid, we need to set the width of the column by using grid-template-columns. We can set by percentage or fr unit (a “fraction”). In the below example, I write it as “grid-template-columns: repeat(4, 1fr)”, “grid-template-columns: 25% 25% 25% 25%”, “grid-template-columns: auto auto auto auto” or “grid-template-columns: repeat(4, 25%)” Those are the same results.

![img](https://miro.medium.com/max/1400/1*ni8TlCtaLmT1zitNyOzYug.png)

![img](https://miro.medium.com/max/1400/1*gXUVDevMVJV0VaJad3GPVA.png)

When we set grid-template-columns it allows div to match the value we set no matter how many div we have and will follow the same pattern. Let me give you an example as follows:

![img](https://miro.medium.com/max/700/1*tZmBO4HfQKiwq9Zrz4lFXA.png)

**Grid-gap, Grid-column-gap, and Grid-row-gap:**

Next, I’m going to talk about the Grid Gap which is the space between rows/columns. We can choose to use “grid-column-gap” to set the value of Grid columns, “grid-row-gap” to set the value of Grid columns, or “grid-gap” to set the value of Grid rows and columns. This can be seen below:

![img](https://miro.medium.com/max/700/1*FhlLMacukh2BEnp12S-2Pg.png)

**Align-self:**

What if we need a different box alignment? We can set the class of each div that we need to set as align-self and set the value as we want it to be. For this example, I set the align-self of box 1 to start, the align-self of box 2 to center, and the align-self of box 3 to end. This is shown below:

![img](https://miro.medium.com/max/700/1*oY2sqZ4wEMTXuyBRmRLaXw.png)

**Grid-column & Grid-row:**

When you want to set the location and size you can use [grid-column](https://www.w3schools.com/cssref/css3_pr_align-self.asp) and [grid-row](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row). For example, I need box 1 to start at 1 and end at 3 for the columns & rows. As you can see, the star represents the columns and the hexagon represents the rows. When you set grid-column: 1/3, it means you start at star 1 and end at star 3. When you set grid-row: 1/3, it means you start at hexagon 1 and end at hexagon 3.

![img](https://miro.medium.com/max/700/1*WtVONQnCwcQZkPyJUKNMZw.png)

Here is the original one below before I set grid-column and grid-row:

![img](https://miro.medium.com/max/527/1*kuFYvdOwIt5sq5IrYOoCqw.png)

[Here is a helpful video that outlines how to utilize the CSS Grid Layout.](https://www.youtube.com/watch?v=jV8B24rSN5o&t=1472s)

