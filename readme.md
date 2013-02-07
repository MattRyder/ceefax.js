#ceefax.js
*A BBC Ceefax terminal/emulator in HTML5 & Javascript*

---

ceefax.js is a reproduction of the original TV-based teletext system, developed by the BBC.  

##Features
 * Embeddable into most web pages.
 * Works in any HTML5 based browser, that supports the `<canvas>` element.
 * Fully customisable, pages are loaded via JSON!
 * Pages can be looked up by typing their page numbers.

##So how do I use this?

Fortunately enough, ceefax.js can be up and running with a few lines of Javascript!  
(...and a couple lines of CSS, if you really want to impress!)

    // Load the data from JSON, for our personalised BBC News feed:
    $.getJSON('testdata.json', function( data ) {
      $.each(data, function(i, a) {
        Ceefax.Pages.push(new CeefaxPage(a.page, a.category, a.headline, a.article));
      });
    });

    // Now tell ceefax.js where to find canvas, and how often to update:
    Ceefax.run("myCanvas", 1000/30);

    