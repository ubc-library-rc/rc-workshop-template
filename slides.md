---
layout: default
title: Publishing slides
nav_order: 5
description:
---

# Publishing slides with reveal.js

Workshop sites can include slides in [reveal.js](https://revealjs.com/) format. Slides can be presented <a href="../demo-slide-deck.html" target="_blank">in a separate tab</a> or embedded in a page, like this:

<div style="overflow: hidden;
  padding-top: 56.25%;
  position: relative">
<iframe src="../demo-slide-deck.html" title="demo embedded slide deck" scrolling="no" frameborder="0"
    style="border: 0;
   height: 100%;
   left: 0;
   position: absolute;
   top: 0;
   width: 100%;">
  <p>Your browser does not support iframes.</p>
</iframe>
</div>

## Create a slide deck

Reveal.js is a presentation framework for creating slide decks with html. To create a new slide deck copy the code chunk below into a new file and save it to the workshop repository as an `.html` file. Notice the <section> elements near the middle; each <section> element corresponds to a slide. Update the `<title>` and `<section>` elements with your own content.

```html
<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8">

  <!-- Title of page (as it will appear in search results) -->
  <title>A demo slide deck</title>

  <meta name="apple-mobile-web-app-capable" content="yes">
	<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">

	<meta name="viewport" content="width=device-width, initial-scale=1.0">

	<link rel="stylesheet" href="https://ubc-library-rc.github.io/reveal-ubc/css/reset.css">
	<link rel="stylesheet" href="https://ubc-library-rc.github.io/reveal-ubc/css/reveal.css">
	<link rel="stylesheet" href="https://ubc-library-rc.github.io/reveal-ubc/css/ubc.css" id="theme">

	<!-- Theme used for syntax highlighting of code -->
	<link rel="stylesheet" href="https://ubc-library-rc.github.io/reveal-ubc/lib/css/monokai.css">

	<!-- Printing and PDF exports -->
	<script>
		var link = document.createElement( 'link' );
		link.rel = 'stylesheet';
		link.type = 'text/css';
		link.href = window.location.search.match( /print-pdf/gi ) ? 'https://ubc-library-rc.github.io/reveal-ubc/css/print/pdf.css' : 'https://ubc-library-rc.github.io/reveal-ubc/css/print/paper.css';
		document.getElementsByTagName( 'head' )[0].appendChild( link );
	</script>

	<!--[if lt IE 9]>
	<script src="lib/js/html5shiv.js"></script>
	<![endif]-->
</head>

<body>

  <div class="reveal">

	<!-- Any section element inside of this container is displayed as a slide -->
		<div class="slides">

      <section>
        <h2>A demo slide deck</h2>
      </section>

      <section data-background="#e6f7ff">
        <h3>Third slide</h3>
        <p>Just an example to illustrate how reveal.js works</p>
      </section>

      <section>
        <h3>Fourth sample slide, a list</h3>
      </section>		      

      <section data-background="#002145">
               <h3>UBC Library Research Commons</h3>
               <blockquote>A multidisciplinary hub supporting research endeavours, partnerships, and education.</blockquote> <blockquote>We are a community space that embraces both new and traditional exploratory scholarship and provides access to services and expertise for the advancement of research. </blockquote>
             </section>

            <section data-background="#002145">

           More from the Research Commons:
               <ul>
               <li><a href="https://researchcommons.library.ubc.ca/">researchcommons.library.ubc.ca</a></li>
               <li><a href="https://researchcommons.library.ubc.ca/events/">Upcoming Events</a></li>
               <li><a href="https://researchcommons.library.ubc.ca/oer/">Open Educational Resources</a></li>
               </ul>
             </section>

		</div>

	</div>

	<script src="https://ubc-library-rc.github.io/reveal-ubc/js/reveal.js"></script>

	<script>

		// More info https://github.com/hakimel/reveal.js#configuration
		Reveal.initialize({
			controls: true,
			progress: true,
			center: true,
			hash: true,

			transition: 'none', // none/fade/slide/convex/concave/zoom

		// More info https://github.com/hakimel/reveal.js#dependencies
			dependencies: [
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/markdown/marked.js', condition: function() { return !!document.querySelector( '[data-markdown]' ); } },
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/markdown/markdown.js', condition: function() { return !!document.querySelector( '[data-markdown]' ); } },
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/highlight/highlight.js' },
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/search/search.js', async: true },
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/zoom-js/zoom.js', async: true },
				{ src: 'https://ubc-library-rc.github.io/reveal-ubc/plugin/notes/notes.js', async: true }
				]
			});

	</script>

	</body>
</html>
```

Reveal.js slide decks have many formatting and display options - [see here](https://github.com/hakimel/reveal.js) for more information.

The html file containing your slide deck will not appear in the navigation menu of your workshop site. To make it visible you can either link to it from one of the website content pages, or embed it in a page.

### Link to the slide deck

 Simply add a link to the slide deck html to one of the .md pages in the site. Recommended practice is to open the slide deck in a new tab using the `target="_blank"` attribute.

```html
<a href="demo-slide-deck.html" target="_blank">View slides in new tab</a>
```
The link to the slides is relative to the page where they're linked from.
{: .caution}

## Embed slides on a page

An alternative is to embed the slides into one of the pages in your workshop site. Add this code to the .md page where you'd like the slides to appear and change the iframe `src` and `title` attributes to point to your html slides.

```html
<div style="overflow: hidden;
  padding-top: 56.25%;
  position: relative">
  <iframe src="demo-slide-deck.html" title="demo embedded slide deck" scrolling="no" frameborder="0"
    style="border: 0;
   height: 100%;
   left: 0;
   position: absolute;
   top: 0;
   width: 100%;">
   <p>Your browser does not support iframes.</p>
 </iframe>
</div>
```

This code ensures the slides will resize to fit the available space. It's written for slides displayed in a 16:9 aspect ratio but you can change the aspect ratio by changing the `padding-top` percentage. For 16:9 the percentage equals 9/16, or 0.5625 (56.25%). For a 4:3 aspect ratio the percentage would be 3/4, or 0.75 (75%).
