![A meme where one bird wants to use semantic HTML elements but a crow is just squawking “div” over and over again.](https://miro.medium.com/max/1400/1*tBkBBEnKeOGo7eUaMW2GxA.jpeg)

To use a word semantically is to use it in the correct way. Writing HTML semantically is very similar. It means that the tags you use must describe the content that is inside them. For example, your footer should be a <footer>, not a <div>. Another common pitfall is choosing HTML tags based on what they will look like on the page. What the page is going to look like should have nothing to do with the HTML tags you should choose. Leave that completely to CSS.

# Why use Semantic HTML?

**1.Accessibility**

Using semantic elements makes a huge difference for people that are using screen readers. If your markup is more meaningful and logically constructed, someone with using a screen reader will have a much better time navigating it.

**2. Search Engine Optimization**

Writing HTML semantically makes it easier for search engines and browsers to understand the content. For example, lets say you wrote an article about a local news story. You could easily put your article in a <div>, and use a p tag for the header. However, you should instead use an article tag and a h1 tag. A search engine will be able to recognize when your content is relevant much more easily.

**3. Ease of Maintenance(for yourself and others)**

If you don’t use semantic HTML, large projects can quickly become confusing and difficult to maintain. It will be especially difficult for other people to work on your code. It’s really easy to confuse one <div> with another. A <header> and a <footer> are a bit more difficult to mix up.

All three of these reasons for using Semantic HTML have something in common. They have to do with helping other people understand the code you write and the websites you create. If it helps everyone else and keeps you organized, why not do it?

The purpose of this article is not to tell you what tag to use in every single situation. That would be crazy. If you are unsure about what element to use you can just look it up! [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html) has fantastic documentation on every single HTML element. They also have articles specifically about Semantic HTML, including complete lists of which elements are Semantic.

One thing to keep in mind is that an element is only truly Semantic if you are using it appropriately. A <footer> may be a Semantic element, but not if you are using it instead of a <header> or a <nav>. The name alone is not what makes the element semantic.

# A few bad habits to look out for

**1.Using HTML for aesthetic purposes**

For example, using a <ul> tag for indentation. While it may be tempting to quickly indent some content this way, this is definitely a job for CSS. Another common example is using a heading tag to change font size rather than the CSS font-size property.

**2. Using anything other than <button> to represent a button**

The most frequent offenders here are <div> and <span>. It won’t make sense to anyone using a screen reader, a co-worker, or a search engine.

**3. Putting everything inside a <div> by default**

For example, having your header, footer and nav all be <div> tags with class names of “header”, “footer”, “nav,” etc(this is probably the one that I have been most guilty of).

**4. Bad heading practices**

Never have more than one <h1> tag. Semantically, you should only have a single <h1> per page, and it should match your title. Your headings should also get smaller as you go down the page. Try to avoid skipping any heading levels.

Thank you for reading!