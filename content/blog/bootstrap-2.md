---
title: 'BOOTSTRAP buttons, colors, cards'
date: 2022-08-29T23:39:08+05:30
tags: ['bootstrap', 'buttons', 'cards', 'bg-color', 'free-images']
series: ['blogs']
showDate: true
draft: false
---

## Bootstrap buttons and cards

> Bootstrap provide predefined styles for buttons and cards.
> Cards can be small containers having header, image, text, content, footer, etc.
> Controlling element width, text styles.

Key points gone through

- Styling buttons {(class="btn")}
  - Outline buttons {(class="btn-outline")}
- Colors
  - Use and available colors
  * bg-'color'
  * primary, secondary, dark, success, danger, light...
- Card containers {(class="card")}
  - card-header
  - card-body
  - card-footer
  - card-text
  - card-group
- Controlling width {(w-50, w-60) widths % in space}
- Text-muted

### Brief explanation

As Bootstrap provides predefined styles for elements like **buttons** and some preset styles like `card`, we can use those styling properties to control element styles.

#### Button

Bootstrap provides stylized buttons as of MaterialUI by default, these can be used by providing class `btn` to an block html element.

There is another style outline buttons, which look like plain buttons with border color. for these we use `btn-outline` on a block element to make it look like outline button.

#### Colors

Colors can be controlled for any element by providing `bg-{color}` as a class, as the basic provided colors of material ui are primary, secondary, light, dark, success, danger, etc...

eg : `bg-primary` sets background of provided element to primary color. (of Material UI).

#### Card

A Card(`card`) is a predefined class provided by bootstrap. It provides basic border styles, color, text styles and text separation and arrangement needed in a card like element.

A card can contain subclasses like `card-header` for providing card heading, `card-body` and `card-footer` for body and footer. when provided a `card-text` class to the text element will style it accordingly to the card.

A `card-group` is a class used when grouping multiple cards or when styling multiple elements to look alike `card`(s).

#### Widths

Controlling the width of a element in controlled styling environment is easy, this can be achieved with bootstrap by providing width percentage of the containing(parent) element. as `w-30`, `w-60`. translates to 30% width and 60% width respectively.

#### Text Disabled/Muted

When styling text, when need to show some **inactive text**, we can use `text-muted` class to show text with less opacity and as inactive.
