# Evernote LESS Structure Boilerplate

After reading the book [SMACSS](http://smacss.com/) and finding it very helpful the Front End team at Evernote has used some of the ideas in our LESS build. We've found breaking the LESS files out into directories (Base, Layout, Modules, and Views) helps organize our files in a project and compile CSS into a clean, logical file. Each page has a LESS (.less) file created that acts as a project file that imports the individual modular components from Base, Layout, Modules, and Views that are needed to build the particular page.

This build methodology is currently being used on [Evernote.com](https://evernote.com).

## Install

```js
npm install evernote-less -g
```

## Use
Run ```evernoteless``` in a directory where you'd like to use the Evernote Less build.

To create new individual Less files run ```evernoteless-page name=filename path=Path-To-Less-directory```. If the name isn't set the file will be named 'page' and if the path isn't set it assumes the directory is 'less'.

To create new Less module run ```evernoteless-module name=filename path=Path-To-Less-Modules-directory```. If the name isn't set the file will be named 'module' and if the path isn't set it assumes the directory is 'less/modules'.

LESS Directories
----------

1.  Base

  The base directory contains styles that help start a project. The base directory could contain the following type of LESS files:
  * Vendor dependancies (Compass, Foundation)
  * Authored dependancies (Mixins, variables, Extends)
  * Fonts
  * Reset

2.  Layout

  The layout directory contains styles that are large containers of a page. This directory could include LESS files like:
  * Responsive Grid
  * Page specific layouts

3.  Modules

  The modules directory will probably contain the bulk of your LESS files. A page may consist of multiple modules and should be styled individually. These modules may include files like:
  * Header
  * Footer
  * Navigation
  * Content Block

4.  Views

  The views directory contains any specific styles that a page may need to change from the generic layout or modules. For example the header in your website maybe green throughout a website or application but on a specific page you want it to change to a blue background that's where the views files would come in.

## Rules

  - There should only be a maximum of 2 CSS files per page ( this prevents HTTP requests )
  - One line for each selector or rule
  - List related items together
  - Only nest 3 levels deep
  - Break files out into small modules (avoid having a Less file that is larger than 100 lines)
  - Avoid using IDs throughout the site. Use IDs for parent elements. Example: Header, Footer, Main. Using Classes avoids having to use !important 
  - Be generous with commenting
  - If a ```:hover``` pseudo class is styled, ```:focus``` should also be styled for accessibility.

## Commenting
  - Using "// " for your comments in Less and they will not output in the compiled CSS


## Variables
  - Any values commonly throughout the LESS build should be set as a variable (fonts, colors, percentages, z-index)
  - All colors should be variables


## Order of imports
  - Vendor dependancies (compass)
  - Authored dependancies (Mixins, variables)
  - Base styles ( reset, fonts, typography )
  - Layout styles
  - Modules styles
  - Views styles

## Release History
* 1.0.1: Remove generated mixins directory.
* 1.0.0: Initial release.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

