---
title: General Questions
layout: layouts/page.njk
permalink: /questions/general-questions/index.html
---

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* When building a new web site or maintaining one, can you explain some techniques you have used to increase performance?
* Can you describe some SEO best practices or techniques you have used lately?
* Can you explain any common techniques or recent issues solved in regards to front-end security?
* What actions have you personally taken on recent projects to increase maintainability of your code?
* Talk about your preferred development environment.  
windows vscode chrome

* Which version control systems are you familiar with?  
Git, TFS(Team Foundation Server)

* Can you describe your workflow when you create a web page?  
That’s a bit open-ended.  
Make an index.html file and drop in a snippet so I can quickly lay out a simple HTML page.  
Add a library if I need it.  
Make an app.js and start coding, etc.

* If you have 5 different stylesheets, how would you best integrate them into the site?  
I try to avoid CSS and just use a library (like Bootstrap). I'd combine the application specific ones into one file. I’d want Bootstrap (or whatever) separate to ensure it is easy to update in the future. I’d also run a tool to find unused css.

* Can you describe the difference between progressive enhancement and graceful degradation?  
Progressive enhancement refers to a feature of your web site that enhances the experience for browsers that support it, but has no impact if your browser does not. Modern browsers get a benefit, older browsers don’t get screwed.  
Graceful degradation is starting with designing the most optimal browser experience, then designing fallbacks for older browsers.

* How would you optimize a website's assets/resources?  
Optimize images.  
Concatenate and minify JavaScript and CSS files.  
Use CSS sprite sheets and icon fonts.  
Use CDN.  
Cache static files (in the past this would be typically done with a php header, but now you could use a HTML5 Cache Manifest).

* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?  
  Depends on the browser. ConnectionsPerHostname For Chrome it is 6, Firefox 6, IE11 is 8 though.
  [(table on this stat)](http://www.browserscope.org/?category=network&v=1)  
  When we use several subdomains pointing the same domain, we can increase the concurrency level of the download.
  
* Name 3 ways to decrease page load (perceived or actual load time).  
Reduce http requests.
Minimize images.  
Minify and concatenate JS/CSS.  
Use a CDN.  
Show spinner or progress bar.  
Preload the page.

* If you jumped on a project and they used tabs and you used spaces, what would you do?  
Conform to the conventions (stay consistant). Introduce a linter or configure editors to ensure indentations are consistent.

* Describe how you would create a simple slideshow page.  
Use a good component or plugin...

* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.  
Standards describe how a thing does and should work. It is extremely important especially in software, because the thing can be used by many people for different perposes.

* What is Flash of Unstyled Content? How do you avoid FOUC?  
It is caused when content is loaded before styles are applied to the content. It happens when style tags are placed after other content, or applied asynchronously, for example, by scripts.  
To avoid FOUC, The easiest way is to place <style> and <link> in the <head>, and avoid applying styles by scripts at the first load.
  
* Explain what ARIA and screenreaders are, and how to make a website accessible.  
They are for accessibility. Use "Semantic HTML" and related attributes, like alt attribute to <img> tags.

* Explain some of the pros and cons for CSS animations versus JavaScript animations.  
CSS3 animations run in a separate thread than JavaScript, so its very non-blocking. So CSS3 is best if your application has some load to it.  
CSS3 animations are also often hardware accelerated (the animation runs on the GPU instead of the CPU boosting performance). But so are many JavaScript animation tools. The triggering of CSS3 animations is generally through the adding and removing of dom classes from JavaScript.

* What does CORS stand for and what issue does it address?  
CORS stands for cross-origin resource sharing. There could be situation where some resources should be allowed from sources having different origin. CORS is a standard to enable cross-site HTTP requests for:
AJAX API call
Web Fonts
WebGL textures
Image/video frames drawn to a canvas using drawImage
Stylesheets
Scripts

* How did you handle a disagreement with your boss or your collaborator?
* What resources do you use to learn about the latest in front end development and design?
