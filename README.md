# jQuery.scrolling

This plugin adds the *scrollin* and *scrollout* events to jquery: these events will fire when any given element becomes visible/invisible in the browser viewport, allowing you to:

- automatically or programmatically show/hide any HTML content as soon as it comes inside or outside the browser viewport (i.e. when the user scrolls to them).
- prevent unnecessary processing for content that is hidden or is outside of the browser viewport.
- trigger a custom function or behaviour (such as loading external AJAX content) when a certain point of the page is reached.

and more.

The plugin also supports *frame*, *iframe* and/or *dynamically-generated* content.

Requires jQuery 1.7 or above.


# Home Page

For the latest package, documentation, API and support please refer to the project <a href="http://darkseal.github.io/jquery.scrolling/">Home Page</a>.


# Installation

Installing the plugin is easy: all you need to do is download the latest version from the official project page (<a href="https://github.com/Darkseal/jquery.scrolling/tarball/master">tar</a> or <a href="https://github.com/Darkseal/jquery.scrolling/zipball/master">zip</a>): unpack the archive somewhere, copy the .js file in your website javascript folder and add the following line to the *head* block of your web page:

        <script type="text/javascript" src="/yourpath/jquery.scrolling.js"></script>


# Usage

Activate the plugin for one or more elements defined by a selector:

        $('selector').scrolling(); 

Or for raw DOM nodes created using the standard jQuery syntax:

        $('<div>content</div>').scrolling(); 
        
Once activated, you can bind your code to the *scrollin* and *scrollout* events: they will trigger when the active element(s) will come inside the browser viewport.

        $('selector').on('scrollin', function(event, $all_elements) {
          // we reach this point as soon as the 'selector' element becomes visibile inside the browser viewport.
          // $all_elements contains all the appeared elements.
        });
        
        $('yourselector').on('scrollout', function(event, $all_elements) {
          // we reach this point as soon as the 'selector' element goes outside the browser viewport.
          // $all_elements contains all the disappeared elements.
        });

If you want to fire the *scrollIn* event for elements which are close to viewport but are not visible yet you may either:
- use the offsetTop and offsetLeft *options* properties during initialization.
- add the following custom data attributes *offset-top* and *offset-left* to DOM nodes.

        $('#myEl').scrolling({ offsetTop: 100 }); 
        // appear will be fired when "myEl" is 100 or less pixels
        // below browser viewport 

or

        <div id="myEl" data-offset-top="100">...</div>
        // same as above using data attributes.

Appear check can also be forced by calling *$.checkScrolling()*. This is suitable in cases when page is in initial state (not scrolled and not resized) and when you want manually trigger appearance check.

There's also a custom *scrollin* jQuery filter you can use for manual checking if the element is inside the viewport or not.

        $('selector').is(':scrollin')


# Demo and Examples

Check the project <a href="http://darkseal.github.io/jquery.scrolling/demo.html">demo page</a> to see the most common implementation scenarios.


# Related links

- <a href="http://darkseal.github.io/jquery.scrolling/" target="_blank">Project Home Page</a>, where you can dowload the latest version.
- <a href="https://github.com/Darkseal/jquery.scrolling" target="_blank">GitHub repository</a>, where you can review the source code and/or fork it to your needs.
- <a href="https://www.npmjs.com/package/jquery.scrolling" target="_blank">jquery.scrolling official page</a> on NPM.org, the node.js repository of most jQuery plugins.
- <a href="http://www.ryadel.com/works/jquery-scrolling/" target="_blank">jquery.scrolling project page</a> on the author website.


# Credits

This is a revamp/upgrade of the jquery.appear plugins respectively hosted on:
- http://code.google.com/p/jquery-appear/
- https://github.com/morr/jquery.appear

The original code has been rewritten and updated in order to support additional features, namely:
- IFrame support
- more options
- configurable values
- revised documentation
- additional samples
and more.

# Support
You can support this project's development by clicking on the following button.
  
[<img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" border="0" alt="Donate">](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VCYVYT76A3QEJ)
  
Thanks a lot!

# License

> Licensed under <a href="http://opensource.org/licenses/MIT">MIT license</a>.
>
> Permission is hereby granted, free of charge, to any person
> obtaining a copy of this software and associated documentation
> files (the "Software"), to deal in the Software without
> restriction, including without limitation the rights to use,
> copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the
> Software is furnished to do so, subject to the following
> conditions:
>
> The above copyright notice and this permission notice shall be
> included in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
> EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
> OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
> NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
> HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
> WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
> FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
> OTHER DEALINGS IN THE SOFTWARE.
