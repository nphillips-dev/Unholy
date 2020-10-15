# Unholy
A random thought which got carried away into an idea which became a light weight CSS "framework"

I had an idea of "oh I wonder what making a framework for CSS is like" but forgot im a jack of all trades and a master of none and I didn't know how to do that.

Instead I went insane, combining the features of about about half a dozen different frameworks into one tiny one. Enough power to give a grid with some components.

So will I work on this more?? Maybe, it was a pointless 5 minute (okay 2 days) experiment but it was educational.

Feel free to pull down, mangle and use to your hearts content but please, please give visit and use the work of the people who know what they are doing and actually worked hard on beautiful things for you all and not this unholy abomination!

* Buttons: https://fdossena.com/index.php?p=html5cool/buttons/i.frag
* Colours: https://design-system.service.gov.uk/styles/colour/
* Form / navbar: https://www.w3schools.com/howto/howto_css_responsive_form.asp
* Cards based on: https://materializecss.com/
* List items: https://getbootstrap.com/
* Ideas and inspiration from:
* https://milligram.io/
* http://getskeleton.com/

N.B. People of the links, if I angered you by involving your code in this nightmare then ping me and I'll cut it out! 

## Installation

Pull down a copy of the project, or see the latest release files, you will see the following files:
* unholy-core : required file, you must reference this stylesheet to access the responsive html elements
* core/unholy-variable : required folder and file. You **do not** need to reference this but all unholy files use these variable.
                         Editing this file provides site wide restyling to all colours.
* unholy-utility : optional file providing css extention methods e.g. borders, alignment - class can be stacked.
* unholy-navigation : optional file containing different navbars

## Core

The following structure will provide a contain, with a row and a full width column, which contains a single card.

    <div class="container">
        <div class="row">
            <div class="column-full">
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

Available columns are:

* .column-single
* .column-quarter 
* .column-third 
* .column-half 
* .column-threeQuarters 
* .column-full 

Images would be structured as follows:

        <div class="wrapper">
            <img card-img-bottom" src="" alt="">
        </div>

Lists are straight forward:
    
    <ul class="list">
        <li class="list-item">
            Help! I'm trapped in a list.
        </li>
    </ul>

## Navigation

At the time of writing, only a single navigation option has been added.

    <div class="w3-nav">
        <a href="#">Home</a>
        <a href="#">Stuff</a>
        <a class="active" href="#">Things</a>
    </div>

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
    --unholy-background: #333 !important;
    --unholy-font: #f2f2f2 !important;
    --unholy-main: #d4351c !important;
    --unholy-secondary: #cf4530 !important;
    --unholy-border: rgba(212, 53, 28, 0.25) !important;
    }

The default theme is all black and red but all the unholy files use var() placeholders. Why?
Because now you've only got to change those variable colours and the whole of your site restyles.

## Pros / Cons

The idea here is you can build a quick and dirty site. It works on the idea that your main theme colour is going to be used in multiple places and for different jobs, which might be restrictive to some really flashy front end humans but for those with the style sense of a fish i.e. me, this is a nice quick way to style a site.