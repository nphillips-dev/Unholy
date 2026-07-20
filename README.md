# Unholy
A random thought which got carried away into an idea which became a lightweight CSS "boilerplate".

I had an idea of "oh I wonder what making a framework for CSS is like" but forgot I'm a jack of all trades and a master of none and I didn't know how to do that.

Instead, I went insane, combining the features of about half a dozen different frameworks into one tiny one. Enough power to give a grid with some common components (see References at the end of the Readme).

## Why??

My experience of front end frameworks is that, out of the box they are great, customising them can be a faff.

The idea here is you can build a quick and dirty site. It works on the concept that your theme colours are going to be used in multiple places and for different jobs, for example:

Active nav item and a submit button - both need separate CSS written but in Unholy both use the same colour variable, change that variable and both elements restyle. See section on variables.

I appreciate this might be restrictive to some really flashy front end humans, I've tried to make this easy to override (no `!important`) but for those with the style sense of a fish i.e. me, this is a nice quick way to style a site.

## Version 3.0.0 (The Modernization Rewrite)

**🚨 WARNING: v3.0.0 is NOT backwards compatible with v2.x.x! 🚨** 

For v3, the framework underwent a massive overhaul to meet modern CSS standards. Floats are dead. Brittle margins are dead. Unholy now runs entirely on modern Flexbox, responsive fluid typography (`clamp()`), and Tailwind-inspired atomic utility classes.

Unholy development still adheres to 3 strict 'rules':
1. Any element, component, utility or navigation must implement the core variables.
2. Optional styling (e.g., borders, spacing, backgrounds) should be provided by utility classes where possible.
3. Unholy core cannot be longer than 300 lines long. *(We are currently sitting comfortably around 125).*

## Installation

Pull down a copy of the project, or see the latest release files, you will see the following files:
* `unholy-core.css` : required file, you must reference this stylesheet to access the responsive html elements and grid.
* `core/unholy-variables.css` : required folder and file. You **do not** need to reference this in your HTML, but all unholy files use these variables. Editing this file provides site-wide restyling to all colours.
* `unholy-utility.css` : optional file providing Tailwind-style CSS extension methods (spacing, alignments, borders) - classes can be stacked.
* `unholy-navigation.css` : optional file containing modern flex-based navbars, sidebars, and dropdowns.

## Core Layout & Grid

The grid is now a robust 3-tier Flexbox system. Elements gracefully shift from 1 column (Mobile) &rarr; 2 columns (Tablet) &rarr; 4 columns (Desktop). Spacing is handled automatically via the `gap` property—no more messy padding!

    <div class="container">
        <div class="row">
            <!-- Box Classes: .box-small, .box-medium, .box-large -->
            <div class="box-medium">
                <div class="card">
                    <div class="card-header">
                        Card Header
                    </div>
                    <div class="card-content">
                        Ooo look a squirrel
                    </div>
                    <div class="card-action">
                        <a href="#" class="button">Click Me!</a>
                    </div>
                </div>
            </div>
        </div>  
    </div>

Images are naturally responsive, no special structure required:
    
    <img src="" alt="">

Tables adhere to K.I.S.S principles - wrap them in a `table-container` div to ensure horizontal scrolling on tiny phone screens: 
    
    <div class="table-container">
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

## Navigation

The old `.w3-nav` class has been purged. Version 3 uses a highly structured, pure-flex `.navbar` component supporting dropdowns.

### Top Navbar
    <nav class="navbar">
        <a href="#" class="nav-brand">Brand</a>
        
        <div class="nav-links">
            <a href="#" class="nav-item active">Home</a>
            <a href="#" class="nav-item">About</a>
        </div>
        
        <!-- Pushes links to the far right -->
        <div class="nav-links ml-auto">
            <div class="dropdown dropdown-right">
                <button class="nav-item">Options ▾</button>
                <div class="dropdown-content">
                    <a href="#" class="nav-item">Settings</a>
                    <a href="#" class="nav-item">Log Out</a>
                </div>
            </div>
        </div>
    </nav>

### Dashboard Sidebar
Need an admin panel? Drop the `.sidebar` into a flex container:
    
    <nav class="sidebar">
        <a href="#" class="nav-brand">Admin Panel</a>
        <a href="#" class="nav-item active">Overview</a>
        <a href="#" class="nav-item">Analytics</a>
    </nav>

## Utility (Tailwind-Style)

No single site will ever be solely satisfied by a CSS boilerplate. Unholy v3 has shifted to an **atomic utility** mindset. You compose your UI by stacking small, single-purpose classes directly in your HTML.

* Want a primary-colored box with padding and rounded corners? 
  `<div class="bg-main p-4 rounded text-center">`
* Want a list item with a faded text color and a thin border? 
  `<li class="list-item text-muted border-thin">`

**Available Utilities:**
* **Text Alignment:** `.text-center`, `.text-right`, `.text-left`
* **Typography:** `.text-uppercase`, `.text-muted`, `.font-bold`
* **Spacing Scale (0-4):**
  * Margin: `.m-0` to `.m-4`, `.my-0` to `.my-4` (vertical)
  * Padding: `.p-0` to `.p-4`, `.px-1` to `.px-4` (horizontal)
* **Borders:** `.border-thin`, `.border-thick`, `.border-none`
* **Radius:** `.rounded-sm`, `.rounded`, `.curved`, `.circle`
* **Shadows:** `.shadow`, `.shadow-hover`
* **Flex Modifiers:** `.d-flex`, `.flex-col`, `.items-center`, `.justify-center`
* **Theme:** `.bg-main`, `.bg-secondary`

## Variables

The top of each unholy file imports the variables file. For v3, the default theme has been upgraded to a premium, deep dark mode.

    :root {
       /* Deeper, cooler base canvas */
       --unholy-background: #0d1117; 
       /* Slightly lighter elevation for cards and navbars */
       --unholy-surface: #161b22;    
       /* Softer, premium typography colors */
       --unholy-font: #e6edf3;       
       /* Crisper reds */
       --unholy-main: #da3633;       
       --unholy-secondary: #f85149;
       /* Neutral, ultra-subtle structural borders */
       --unholy-border: rgba(255, 255, 255, 0.1); 
    }

Because all files use `var()` placeholders, you only have to change those six variables, and the entire framework restyles itself to your new brand instantly.

## References / Thanks / Inspiration

Feel free to pull down, mangle and use to your heart's content, but please visit and use the work of the people who know what they are doing and worked hard on beautiful things for you all.

* Buttons: https://fdossena.com/index.php?p=html5cool/buttons/i.frag
* Colours: https://design-system.service.gov.uk/styles/colour/
* Form / navbar: https://www.w3schools.com/howto/howto_css_responsive_form.asp
* Ham nav: https://code-boxx.com/simple-responsive-pure-css-hamburger-menu/
* Cards based on: https://materializecss.com/
* List items: https://getbootstrap.com/
* Ideas and inspiration from:
  * https://milligram.io/
  * http://getskeleton.com/
  * Tailwind CSS (for v3 utility inspiration)

N.B. People of the links, if I angered you by involving your code in this nightmare then ping me and I'll cut it out!