---
title: "BOOTSTRAP basics and more..."
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
    * `row-cols` : `row-col` is for specifying styles for columns in a row.
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
    * `align-items` : align-items as in css aligns the items in a vertical axis specified for row.
      ```html
        <div class="row align-items-start">
          <div class="col">
            aligned to start
          </div>
        </div>
      ```
      - `align-items-start` : will align the items to the start/top of the row.
      - `align-items-center` : will align the items to the center of the row.
      - `align-items-end` : will align the items to the end/bottom of the row.
    * `align-self` : As align items but will get applied to the specified element, used on columns.
      ```html
        <div class="row ">
          <div class="col align-self-start">
            aligned itself to start
          </div>
        </div>
      ```
      - `align-self-start` : will align itself to the start/top of the row.
      - `align-self-center` : will align itself to the center of the row.
      - `align-self-end` : will align itself to the end/bottom of the row.
      
    * `justify-content` : will justify content (elements) based on the given attribute class, usually applied to row.
      ```html
        <div class="row justify-content-start">
          <div class="col">
            justified to start
          </div>
        </div>
      ```
      - `justify-content-start` : will align the contents to right/start of row.
      - `justify-content-center` : will align the contents to centre of row.
      - `justify-content-end` : will align the contents to left/end of row.
      - `justify-content-between` : will align the contents to the ends of row.
      - `justify-content-evenly` : will align the contents spaced evenly, space changes based on element sizes.
      - `justify-content-around` : will align the contents keeping the space around the elements.
    * **Margins** : margin is applied to the element to space the element out from other surrounding elements, they can be applied on levels/steps of `1 to 5`.
      ```html
      <!-- margin on all sides at step 5 -->
        <div class="row m-5">
          <div class="col">
            aligned itself to start
          </div>
        </div>
      ```
      - `m-*` : will apply margins on all sides.
      - `mx-*` : will apply margins on left and right sides.
      - `my-*` : will apply margins on top and bottom sides.
    * **Gutter** : gutter can be termed as the `gap` given between elements,just like margin they also can be applied on levels/steps of `1 to 5`.
      ```html
        <div class="row g-5">
          <!-- element gap is applied at step of 5 -->
          <div class="col">
            aligned itself to start
          </div>
        </div>
      ```
      - `g-*` : will apply gutter on all sides.
      - `gx-*` : will apply gutter on left and right sides.
      - `gy-*` : will apply gutter on top and bottom sides.
      

  ####   Regex in CSS
  * Regex is also available in css. cool right! this css works on attributes of a element in the document.
      ```css
        div[class*="regex-"] {
          margin : 10px;
        }
      ```
      - The above syntax will match all classes with prefix of "regex-", for example regex-1, regex-some-any.
      ```css
        li[class^="start-"] {
          margin : 10px;
        }
      ```
      - The above syntax with "^" will match all classes with start of "start-", for example start-something.
      ```css
        div[class$="-end"] {
          margin : 10px;
        }
      ```
      - The above syntax with "$" will match all classes which end with "-end", for example blah-blah-end.

  ####   SCSS basics
  * SCSS is a scripting language based on css, which is written and then used to generate css. This helps in maintaining large contents of styles and they can result in easily editable and maintainable css.
  



### Reason for this blog / discovery
  Just wanted to start documenting things which i learn.
 
 * Source Read more : [Bootstrap](https://getbootstrap.com/docs/5.2/layout/grid/)
