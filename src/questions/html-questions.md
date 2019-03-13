---
title: HTML Questions
layout: layouts/page.njk
permalink: /questions/html-questions/index.html
---

* What does a `doctype` do?  
	* It specifies the version of html the page is using. With the information, the browser determines how to render the page.

* How do you serve a page with content in multiple languages?  
	* Use `lang` (or `xml:lang` for XHTML) in tags. Also metadata and `Content-Language` HTTP header can be used.

* What kind of things must you be wary of when design or developing for multilingual sites?  
	* `<meta charset='UTF-8'>`  
	* `hreflang` attr in link  
	* `dir` attr indicating language direction, such as `rtl`  
	* `font-size` and space for `:lang({language_code})` selectors in CSS

* What are `data-` attributes good for?  
	* Custom data attributes are intended to store custom data private to the page or application, for which there are no more appropriate attributes or elements.

* Consider HTML5 as an open web platform. What are the building blocks of HTML5?  
	* New HTML5 Elements:  
 		* New semantic elements like `<header>`, `<footer>`, `<article>`, and `<section>`.  
 		* New form control attributes like `number`, `date`, `time`, `calendar`, and `range`.  
 		* New graphic elements: `<svg>` and `<canvas>`.  
 		* New multimedia elements: `<audio>` and `<video>`.  
	* New HTML5 API’s:  
 		* HTML Geolocation  
 		* HTML Drag and Drop  
 		* HTML Local Storage  
 		* HTML Application Cache  
 		* HTML Web Workers  
 		* HTML SSE  

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
	* HTML5 web storage - generic term for the new client-side data storage options. Web Storage is more secure and faster. The data is not included with every server request, but used ONLY when asked for. It is also possible to store large amounts of data, without affecting the website's performance.  
 		* HTML5 local Storage - persistant and scoped to the domain (store data with no expiration date).  
      default: stores things in key/value pairs  
      Web SQL (aka Web Database): uses a SQL database  
 		* HTML5 session storage -  non persistent and scoped only to the current window (stores data for one session).  
	* Cookies - the old school way of doing all of the above. Stores things in key/value pairs per domain.

* Describe the difference between `<script>`, `<script async>` and `<script defer>`.  
	* `<script>` stops rendering process, and download and run a script.
	* `<script async>` don't stop rendering process while asynchronously downloading a script. When finishing download, it stops rendering and runs the script.  
	* `<script defer>` don't stop rendering process while asynchronously downloading a script. When finishing rendering, it runs the script. A positive effect of this attribute is that the DOM will be available for your script. However, since not every browser supports defer yet, don’t rely on it.  
###### References: [Difference between async and defer attributes in script tags](https://javascript.tutorialhorizon.com/2015/08/11/script-async-defer-attribute/)
  
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?  
	* Generally speaking you want to have a page’s style information parsed first before the page content is rendered (avoid FOUC).
	* `<script>`s should be referenced just before `</body>`. This prevents render blocking while the scripts load and is much better for site perception speed. Except ajax is being used to load the pages default content.  
	* In modern DESKTOP browsers, it looks like linking to CSS first never provides a performance gain.  

* What is progressive rendering?  
	* Prioritizing visible content (or above the fold rendering) where you include only the minimum css/content/scripts necessary for the amount of page that would be rendered in the users browser first to display as quickly as possible, you can then use deferred javascript (domready/load) to load in other resources and content.

* Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.  
	* `srcset` is a new attribute which allows you to specify a set of images for different viewport sizes/orientation.  
  1. Look at its device width.  
  2. Work out which media condition in the sizes list is the first one to be true.  
  3. Look at the slot size given to that media query.  
  4. Load the image referenced in the srcset list that most closely matches the chosen slot size.  
###### References: [responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
  
* Have you used different HTML templating languages before?
