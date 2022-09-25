---
title: "CSS regex/ attribute selectors"
date: 2022-09-19T19:55:20+05:30
tags: ["css", "regex", "attribute selector"]
series: ["blogs"]
showDate: true
draft: false
---

## Learning Bootstrap, sass/scss. (Large)
Author: self
- Some of my works [Github](https://github.com/rex-suresh)
- Contact through [Email](psureshk9@gmail.com)

### Introduction
> Css supports regex when styling elements, it uses simple regex match syntax using *, ^, $, ~ to match complete, start, end and contains matches.
Things I have learnt.
 - css regex match
  - start match (^); 
  - end match ($); 
  - contains match (~); 
  - complete/followed match (*); 

### Brief explanation
  ####   Regex in CSS
  * Regex is also available in css. cool right! this css works on attributes of a element in the document.
      - The below syntax will match all classes with prefix of "regex-", for example regex-1, regex-some-any.
      ```css
        div[class*="regex-"] {
          margin : 10px;
        }
      ```
      - The below syntax with "^" will match all classes with start of "start-", for example start-something.
      ```css
        li[class^="start-"] {
          margin : 10px;
        }
      ```
      - The below syntax with "$" will match all classes which end with "-end", for example blah-blah-end.  
      ```css
        div[class$="-end"] {
          margin : 10px;
        }
      ```
      - The below syntax with "~" will match all classes which contains with "hi", for example hi-1, hohi, hehihe.  
      ```css
        div[class~="hi"] {
          margin : 10px;
        }
      ```



### Reason for this blog / discovery
  Just wanted to start documenting things which i learn.
 
 * Source Read more : [MDN attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
