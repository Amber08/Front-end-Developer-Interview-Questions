---
title: HTML Questions
layout: layouts/page.njk
permalink: /questions/html-questions/index.html
---

* What does a `doctype` do?  
	* `DOCTYPE` is an abbreviation for DOCument TYPE. It declares Document Type Definition and specifies what version of the HTML specifications the webpage is using. With the information, the browser determines how to render the page.  
  If a user agent doesn't recognize a correct `DOCTYPE`, it will trigger the [quirks mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode).  
  The DOCTYPE declaration recommended by HTML5 is `<!DOCTYPE html>`.

* How do you serve a page with content in multiple languages?  
	* Use `lang` (or `xml:lang` for XHTML) in tags. Also metadata and `Content-Language` HTTP header can be used.

* What kind of things must you be wary of when design or developing for multilingual sites?  
	* `<meta charset='UTF-8'>`  
	* `hreflang` attr in link  
	* `dir` attr indicating language direction, such as `rtl`  
	* `font-size` and space for `:lang({language_code})` selectors in CSS
  * Format of dates and currencies
  * Language reading direction

* What are `data-` attributes good for?  
	* [data- attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) are intended to store custom data private to the page or application, for which there are no more appropriate attributes or elements.  
  These days, using `data-` attributes is not encouraged. One reason is that users can modify the data attribute easily by using inspect element in the browser. The data model is better stored within JavaScript itself and stay updated with the DOM via data binding possibly through a library or a framework.

* Consider HTML5 as an open web platform. What are the building blocks of HTML5?  
	* New [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) Elements:  
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
	* HTML5 [Web storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) - generic term for the new client-side data storage options. Web Storage is more secure and faster. The data is not included with every server request, but used ONLY when asked for. It is also possible to store large amounts of data, without affecting the website's performance.  
 		* `localStorage` - persistant and scoped to the domain (store data with no expiration date).  
      default: stores things in key/value pairs  
      Web SQL (aka Web Database): uses a SQL database  
 		* `sessionStorage` -  non persistent and scoped only to the current window (stores data for one session).  
	* [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies) - the old school way of doing all of the above. Stores things in key/value pairs per domain.

|                                        | `cookie`                                                 | `localStorage` | `sessionStorage` |
| -------------------------------------- | -------------------------------------------------------- | -------------- | ---------------- |
| Initiator                              | Client or server. Server can use `Set-Cookie` header     | Client         | Client           |
| Expiry                                 | Manually set                                             | Forever        | On tab close     |
| Persistent across browser sessions     | Depends on whether expiration is set                     | Yes            | No               |
| Sent to server with every HTTP request | Cookies are automatically being sent via `Cookie` header | No             | No               |
| Capacity (per domain)                  | 4kb                                                      | 5MB            | 5MB              |
| Accessibility                          | Any window                                               | Any window     | Same tab         |
  
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.  
	* `<script>` stops rendering process, and download and run a script.
	* `<script async>` don't stop rendering process while asynchronously downloading a script. When finishing download, it stops rendering and runs the script.  
	* `<script defer>` don't stop rendering process while asynchronously downloading a script. When finishing rendering, it runs the script. A positive effect of this attribute is that the DOM will be available for your script. However, since not every browser supports defer yet, don’t rely on it.  
  Note: The `async` and `defer` attributes are ignored for scripts that have no `src` attribute.
  ###### References: [Difference between async and defer attributes in script tags](https://javascript.tutorialhorizon.com/2015/08/11/script-async-defer-attribute/)
  
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?  
	* Generally speaking you want to have a page’s style information parsed first before the page content is rendered (avoid FOUC).
	* `<script>`s should be referenced just before `</body>`. This prevents render blocking while the scripts load and is much better for site perception speed. Except ajax is being used to load the pages default content.  
	* In modern DESKTOP browsers, it looks like linking to CSS first never provides a performance gain.  

* What is progressive rendering?  
	* Prioritizing visible content (or above the fold rendering) where you include only the minimum css/content/scripts necessary for the amount of page that would be rendered in the users browser first to display as quickly as possible, you can then use deferred javascript (domready/load) to load in other resources and content.
  ###### References
  * [what-is-progressive-rendering](https://stackoverflow.com/questions/33651166/what-is-progressive-rendering)
  * [Async Fragments: Rediscovering Progressive HTML Rendering with Marko](http://www.ebaytechblog.com/2014/12/08/async-fragments-rediscovering-progressive-html-rendering-with-marko/)

* Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.  
	* `srcset` is a new attribute which allows you to specify a set of images for different viewport sizes/orientation.  
  1. Look at its device width.  
  2. Work out which media condition in the sizes list is the first one to be true.  
  3. Look at the slot size given to that media query.  
  4. Load the image referenced in the srcset list that most closely matches the chosen slot size.  
  ###### References
  * [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
  * [Responsive Images: If you’re just changing resolutions, use srcset.](https://css-tricks.com/responsive-images-youre-just-changing-resolutions-use-srcset/)
  
* Have you used different HTML templating languages before?
