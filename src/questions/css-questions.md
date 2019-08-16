---
title: CSS Questions
layout: layouts/page.njk
permalink: /questions/css-questions/index.html
---

* What is CSS selector specificity and how does it work?
  * [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) is a weight that is applied to a given CSS declaration, determined by the number of each selector type in the matching selector. When multiple declarations have equal specificity, the last declaration found in the CSS is applied to the element. Specificity only applies when the same element is targeted by multiple declarations.
  * Inline styles (e.g., style="font-weight: bold;") > 
  ID selectors (e.g., #example) > 
  Class selectors (e.g., .example), attributes selectors (e.g., [type="radio"]) and pseudo-classes (e.g., :hover) >
  Type selectors (e.g., h1) and pseudo-elements (e.g., ::before)
  * Universal selector (*), combinators (+, >, ~, ' ', ||) and negation pseudo-class (:not()) have no effect on specificity. (The selectors declared inside :not() do, however.) 
  * The `!important` exception: When an `!important` rule is used on a style declaration, this declaration overrides any other declarations. Although technically !important has nothing to do with specificity, it interacts directly with it. Using !important, however, is bad practice and should be avoided because it makes debugging more difficult by breaking the natural cascading in your stylesheets.
  * The `:not()` exception: The negation pseudo-class :not() is not considered a pseudo-class in the specificity calculation. But selectors placed into the negation pseudo-class count as normal selectors when determining the count of selector types.
  * Specificity is based on the form of a selector. In the following case, the selector *[id="foo"] counts as an attribute selector for the purpose of determining the selector's specificity, even though it selects an ID.

* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  * **Resetting** - Remove all the native styles provided by browsers. You will have to redeclare styling for common typographic elements.
  * **Normalizing** - [Normalize.css](http://nicolasgallagher.com/about-normalize-css/) preserves useful default styles rather than erasing them. It corrects bugs for common browser dependencies. Normalize.css doesn't clutter your dev tools.

* Describe Floats and how they work.
  * The [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) CSS property places an element on the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the page, though still remaining a part of the flow (in contrast to absolute positioning).
  ###### References
  * https://css-tricks.com/almanac/properties/f/float/
  * https://css-tricks.com/all-about-floats/
  * https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats

* Describe z-index and how stacking context is formed.
  * The [`z-index`](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) CSS property sets the z-order of a positioned element and its descendants or flex items. Overlapping elements with a larger z-index cover those with a smaller one. For a positioned box (that is, one with any `position` other than `static`), the `z-index` property specifies:
  1. The stack level of the box in the current stacking context.
  2. Whether the box establishes a local stacking context.

* Describe BFC (Block Formatting Context) and how it works.
  * A [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with other elements. 
  * A BFC is created by at least one of the following:
    * The value of `float` is not `none`.
    * The value of `position` is `absolute` or `fixed`.
    * The value of `display` is `inline-block`; or `table-cell`, `table-caption`, `table`, `table-row`, `table-row-group`, `table-header-group`, `table-footer-group`, `inline-table`; or `flex`, `inline-flex`; or `grid`, `inline-grid`, or `flow-root`.
    * The value of `overflow` is not `visible`.
    * Elements with `contain: layout`, `content` or `strict`.
    * Elements where `column-count` or `column-width` is not `auto`, including elements with `column-count: 1`
    * `column-span: all`
    ###### References: https://www.sitepoint.com/understanding-block-formatting-contexts-in-css/

* What are the various clearing techniques and which is appropriate for what context?
  * Empty `div` method - `<div style="clear:both;"></div>`
  * Overflow Method - `overflow: auto` or `overflow: hidden`
  * The Psuedo Method - ```* .clearfix:after { content: "."; visibility: hidden; display: block; height: 0; clear: both;}```
  
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
  * #1: visibility: hidden
  * #2: width: 0; height: 0;
  * #3: text-indent: -1000px
  * #4: absolute position off the screen

* Have you ever used a grid system, and if so, what do you prefer?
  * Grid system of Bootstrap and Antd. 

* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* Can you give an example of an `@media` property other than `screen`?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* What is the CSS `display` property and can you give a few examples of its use?
* What's the difference between inline and inline-block?
* What's the difference between the "nth-of-type()" and "nth-child()" selectors?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
