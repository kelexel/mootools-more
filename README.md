MooTools Plugins and Enhancements Repository

### Wiki

* [See the wiki for how to get involved](http://wiki.github.com/mootools/mootools-more).
* See also [MooTools-Core](https://github.com/mootools/mootools-core/tree) and [MooTools-Lang](http://github.com/anutron/mootools-lang/tree/master)

### TO DO

* Need to run tests against all browsers
* Move demo/tutorials from Clientcide wiki to Mootorial; update links in docs
* Go through lighthouse tickets and identify criticals for 1.0 release
* Go through docs files and fix any inconsistencies with -core syntax for docs

### Decisions/discussions
* Decide if reworking the whole source of all plugins makes you an author ( :P )
* Revisit branch commits from other users in github that have not made it into master (http://github.com/anutron/mootools-more/network)

### Server

* need to figure out docs
* need to decide how more is presented w/ regards to -core; http://www.mootools.net/more/* ?
* need to get access to push releases (for Aaron at least - I don't have access now)
* need demos

### StyleGuide

* http://wiki.github.com/mootools/mootools-core/syntax-and-coding-style-conventions

### Breaking Changes from More

* Tips
  - options:offsets in Tips renamed to offset
* Accorion
  - renamed to Fx.Accordion
* SmoothScroll
  - renamed to Fx.SmoothScroll

### Breaking Changes from Clientcide

* IframeShim
  - options:zindex renamed to zIndex
  - makeShim method gone
  - occluded property (Element.storage) now camelcase (iframeShim). consistent with tween, morph, etc
* JsonP
  - renamed to Request.JSONP
  - constructor/send/prepareUrl take options hash, no longer an url directly (like Request)
  - user can change options on the fly when calling send() with a new hash, reusing the object
  - added check method. support for link: ignore, cancel, chain (like Request)
  - added success, request and cancel events
  - data can be a hash or string now (like Request)
  - queryString option gone
  - makeUrl logic now moved to new getScript(), which directly returns the script
  - changed how it essentially works. instead of storing the object reference, we store a new function every time a request is made, that keeps a reference of the script element and the object instance.
  - abortAfter and timeout gone. there's now a single timeout for retries and for when retries run out.
  - globalFunction gone, deemed useless
* Browser.Extras completely refactored into URI Native object
  - Browser.redraw is gone
* Class.Binds no longer supports lowercase binds
* Element.fxOpacityOk (which was never documented or intended for external use) is gone
* FormValidator base class no longer does what it did (that is now in FormValidator.Inline)
* OverText
  - no longer takes a collection of inputs.
  - .showTxt > .show, .hideTxt > .hide
  - .hide and .show no longer take the element and 'focus' arguments.
  - .repositionAll is gone; .repositionOverTxt is now just .reposition; it does not take an argument
* String.Extras
  - findAllEmails gone, too specific
* Date
  - Number / String extensions moved to string extras. zeroise made an anonymous function, was lame
* Element.setPosition is now Element.position
* String.Extra query functions moved to URI.js
 - parseQuery > parseQueryString for consistency with cleanQueryString