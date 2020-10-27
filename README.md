# Unholy
A random thought which got carried away into an idea which became a light weight CSS "boilerplate"

I had an idea of "oh I wonder what making a framework for CSS is like" but forgot im a jack of all trades and a master of none and I didn't know how to do that.

Instead I went insane, combining the features of about about half a dozen different frameworks into one tiny one. Enough power to give a grid with some common components (see References at the end of Readme).

## Why??

My experience of front end frameworks is that, out of the box they are great, customising them can be a faff.

The idea here is you can build a quick and dirty site. It works on the concept that your theme colours are going to be used in multiple places and for different jobs, for example:

Active nav item and a submit button - both need seperate CSS written but in Unholy both use the same colour variable, change that variable and both elements restyle. See section on variables.

I appriciate this might be restrictive to some really flashy front end humans, I've tried to make this easy to override (no !important) but for those with the style sense of a fish i.e. me, this is a nice quick way to style a site.

## Version 2 and Rules

For v2.0.0 I did some research into flexbox, altered some of the core to simplify it but (hopefully) improve the responsiveness. 

Unholy development has 3 'rules':
1. Any element, component, utility or navigation must impliment the core variables
2. Optional styling e.g. borders, should be provided by utility classes where possible
3. Unholy core cannot be longer than 300 lines long

## Installation

Pull down a copy of the project, or see the latest release files, you will see the following files:
* unholy-core : required file, you must reference this stylesheet to access the responsive html elements
* core/unholy-variable : required folder and file. You **do not** need to reference this but all unholy files use these variable.
                         Editing this file provides site wide restyling to all colours.
* unholy-utility : optional file providing css extention methods e.g. borders, alignment - class can be stacked.
* unholy-navigation : optional file containing different navbars

## Core

The following structure will provide a contain, with a row and a full width box, which contains a single card.

    <div class="container">
        <div class="row">
            <div class="box-large">
                <div class="card">
                    <div class="card-header">
                        Card Header
                    </div>
                    <div class="card-content">
                        Ooo look a squirrel
                    </div>
                    <div class="card-action">
                        <a href="#" target="_blank" rel="noopener noreferrer">Click Me!</a>
                    </div>
                </div>
            </div>
        </div>  
    </div>

Inside a row there are 3 types of basic boxes:

* .box-small (22%)
* .box-medium (50%)
* .box-large (100%)

Images do not require special structure:

    <img src="" alt="">

Combine with utility for effects e.g.

    <img class="circle shadow" src="" alt="">
        
Lists are straight forward:
    
    <ul class="list">
        <li class="list-item">
            Help! I'm trapped in a list.
        </li>
    </ul>

Tables adhere to K.I.S.S principles - you need a div wrapper with the `table-container` class
N.B. put it on the row, the column or a new div if you like, doesn't seem to matter. 

    <div class="row">
        <div class="column-full table-container">
            <table>
                <tr>
                  <th>First Name</th>
                  <th>Last Name</th>
                </tr>
                <tr>
                  <td>Spooky</td>
                  <td>Bob</td>
                </tr>
              </table>
        </div>
    </div>

## Navigation

The simplest of responsive nav, no collapsing, all menu

    <div class="w3-nav">
        <a href="#">Home</a>
        <a href="#">Stuff</a>
        <a class="active" href="#">Things</a>
    </div>

Those of a more refined pallet might enjoy this little number

    <nav id="hamnav">
        <label for="hamburger">&#9776;</label>
        <input type="checkbox" id="hamburger"/>

        <div id="hamitems">
            <a href="#">Home</a>
            <a href="#">Stuff</a>
            <a class="active" href="#">Things</a>
        </div>
    </nav>

## Utility

No single site will ever be soley satisfied by a CSS boilerplate, you'll likely create a custom.css file and it'll fill up with the same classes, over and over again.

Utility provides some of those classes, for use as you see fit e.g.

* Oh no! My cards are so boring! `<div class="card shadow">`
* Oh no! My lists are left aligned! `<li class="list-item centered">`
* Oh no! My lists are left aligned **AND** not curvey enough: `<li class="list-item centered rounded">`

* Text alignment
  * center
  * right
  * left
* borders
  * shadow
  * thin
  * thick
  * rounded
  * curved
  * circle
  
## Variables

The top of each unholy file imports the variables file:

    :root {
    --unholy-background: #333;
    --unholy-font: #f2f2f2;
    --unholy-main: #d4351c;
    --unholy-secondary: #cf4530;
    --unholy-border: rgba(212, 53, 28, 0.25);
    }

The default theme is all black and red but all the unholy files use var() placeholders. Why?
Because now you've only got to change those variable colours and the whole of your site restyles.


## References / Thanks / Inspiration

Feel free to pull down, mangle and use to your hearts content but please, please visit and use the work of the people who know what they are doing and worked hard on beautiful things for you all.

* Buttons: https://fdossena.com/index.php?p=html5cool/buttons/i.frag
* Colours: https://design-system.service.gov.uk/styles/colour/
* Form / navbar: https://www.w3schools.com/howto/howto_css_responsive_form.asp
* Ham nav: https://code-boxx.com/simple-responsive-pure-css-hamburger-menu/
* Cards based on: https://materializecss.com/
* List items: https://getbootstrap.com/
* Images: https://www.freecodecamp.org/news/time-saving-css-techniques-to-create-responsive-images-ebb1e84f90d5/ 
* Ideas and inspiration from:
* https://milligram.io/
* http://getskeleton.com/

N.B. People of the links, if I angered you by involving your code in this nightmare then ping me and I'll cut it out! 