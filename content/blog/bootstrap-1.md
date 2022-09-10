---
title: "Bootstrap basics and so many..."
date: 2022-08-28T21:55:34+05:30
# tags: ["bootstrap", "sass", "scss", "css", "regex"]
# series: ["blogs"]
showDate: true
draft: false
---

## Learning Bootstrap, sass/scss. (Large)
Author: self
- Some of my works [Github](https://github.com/rex-suresh)
- Contact through [Email](psureshk9@gmail.com)

### Introduction
> Boot strap is a css framework which is used by developers to make mobile first and responsive webpages quickly.
> scss is a scripting language, which is compiled and used for generating css.

Things I have learnt.
 - Bootstrap fundamentals
    - containers
    - grid
      - breakpoints
      - column separation
        - fluid
        - auto
      - predefined classes
        - row
        - col
        - row-col-*
        - align-items-*
        - justify-content-*
      - (mx-, my-, m-) margin
      - (gx-, gy-, g-) gutter
 - css regex match
 - scss basics
  - nesting and @use


### Brief explanation
  Bootstrap uses grid layout of 12 columns to determine predefined sized of elements in screen.
  It mimics the designs of material UI
  Because mobile screens are small, the websites which load on them are loaded in a virtual viewport and 
  are scaled accordingly to the device screen. for making a website to work for both a mobile and computer screen,
  we can provide "meta" tag for html to say it to render that html optimized for mobile screen:
  
   `<meta name="viewport" content="width=device-width, initial-scale=1">`


  #### Containers : Basic wrappers around content in html.
    .container » is a class predefined to apply further styles and arrangements
  #### Breakpoints : As stated bootstrap uses grid to determine the arrangements of elements,
  the element sizes can be defined for responsiveness.
    * > for example : a box can fill half screen size at full screen mode and full screen at half screen mode.
    * for the purpose of providing breakpoints, we can use some suffixes
      - container-xs : extra small size
      - container-sm : small size
      - container-md : medium size
      - container-lg : large size
      - container-xl : extra large
      - container-xxl : double extra large
      - container-fluid : completely fills the space as fluid.
      - container-auto : adjusts accordingly based on content to be shown on one row size.
    
  #### Column separation : Bootstrap uses 12 column grid for aligning items and using break points. 
  These breakpoints bu default are set to `full width` mode. This can be achieved by just providing `container`
    * Fluid : fluid is a element class which renders the element filling the whole screen width.
      - can be used as `container-fluid`
    * Breakpoint : Container can be sized based on break points such that the defined size will be maintained till the breakpoint and them converted to `container-liquid`
      - can be used as `container-{breakpoint}` example: `container-sm`, `container-md`...

  ####   Predefined classes : Elements can be styled / sized accordingly by providing breakpoints and sizes as classes.
   
  * Using bootstrap we can use some class names like :
    * `row` : row is for specifying that the element is a row element.
      ``` html
        <div class="row">
          <div class="col">col 1</div>
          <div class="col">col 2</div>
          <div class="col">col 3</div>
        </div>
        <div class="row">
          <div class="col">col 1</div>
          <div class="col">col 2</div>
        </div>
      ```
      - In this given instance the `row` controls the width of based on their count, as they are not specifically styled
      - > just as a flex container having elements with width as 100% and container controlling width as per their count.(if not wrapped)
    * Full width: col is for specifying that the element is a column element.
      - just using `col` will allow element to fill most the space available for it.
      ``` html
        <div class="row">
            <div class="col">col 1</div>
            <div class="col">col 2</div>
            <div class="col">col 3</div>
        </div>
      ```
      - Manual sizing:  giving different `col-{size}` values will result in size accordingly
      ``` html
        <div class="row">
            <div class="col-1">col 1</div>
            <div class="col-8">col 2</div>
            <div class="col-3">col 3</div>
        </div>
      ```   
      - Sizing with auto length:  using `col-{breakpoint}-auto` will allow the element to size according on its contents (auto),

      ``` html
        <div class="row">
            <div class="col">col 1</div>
            <div class="col-lg-auto">col 2</div>
            <div class="col-1">col 3</div>
        </div>
      ```
      - Mix and match:  using `col-{breakpoint}-{size}` will allow the element to maintain size up to given breakpoint and once viewport is less than that it will take the give size.
      ``` html
        <div class="row">
          <div class="col-12 col-xxl-4">1</div>
          <div class="col-12 col-xxl-4">2</div>
        </div>
      ```
      - actual size `col-2` after view port being less than `-lg` breakpoint actual size is applied. Until then size will be `-fluid` fill
    * `row-cols` : `row-col` is for specifying styles columns for row.
      ```html
        <div class="row row-cols-3">
          <div class="col">1</div>
          <div class="col">2</div>
        </div>

        <!-- This will style the columns as per the size of the view port -->
         <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4"></div>
      ```
      - `row-cols-2` : will make 2 columns to fit in a row, and only if there are no specific class styles except `col` is specified.
      - `row-cols-5` : will make 5 columns in a row and which will get sized according to view port size.


### Reason for this blog / discovery
  Just wanted to start documenting things which i learn.
 -- Source Read more : [Bootstrap](https://getbootstrap.com/docs/5.2/layout/grid/)
