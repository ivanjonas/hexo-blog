title: In-place CSS framework migration
tags:
  - css
  - tools
  - development
  - migration
category: Software Development
date: 2016-02-11 02:44:37
---

A long-sh absence of two months is due to me taking on a new position that actually pays money! After five months of being on sabbatical, I finally realized how nice it is to have cash flow. 

Anyway, I'd like to share the monumental project I've been undertaking for my employer (whose opinion I do not represent in any capacity; my words are my own; etc, etc). When I started there, they lacked the manpower to transition from an early CSS framework called Skeleton, which, to be honest, is not bad! But 1: it does not support IE8, which we are committed to doing for grudgingly legitimate reasons, and 2: our web site has grown into a big product, so Skeleton's minimalism is not suitable for our web site. So I set about figuring out how to transition. 

We had plenty of pages built on* skeleton. We wanted to build new pages on Bootstrap. But the most challenging requirement is that we wanted to use Bootstrap in the header and footer of every page (but not the body) to trigger Bootstrap modals. In effect, we needed both frameworks on existing pages, and we needed them to not conflict. 

\* (In actuality, skeleton.css loaded *after* our custom styles. There are, no doubt, specificity battles because of this unfortunate fact.)

Less to the rescue! [Less](http://lesscss.org/) is a CSS preprocessor that allows us to treat CSS more like code and less like markup. (Although I prefer [Stylus](http://stylus-lang.com/) for its flexible syntax and more powerful functions, Less was already established in my organization). Using Less, I was able to easily prepend a class to *every single rule* in Bootstrap. This:

```less
.container {
    .inner {
        color: blue;
    }
}
```
evaluates to:
```css
.container .inner {
   color: blue;
}
```

so this:
```less
.bootstraptransition {
    @import "../../lib/bootstrap";
}
```
evaluates to this:
```css
...
@media (min-width: 1200px) {
    .bootstraptransition .container {
        width: 1170px;
    }
}
...
.bootstraptransition .row {
    margin-right: -15px;
    margin-left: -15px;
}
...
```

This allowed me to apply bootstrap **only** to specific elements on the page. However, this introduced a problem. Every rule increased its specificity by 0|0|1|0 ([learn about specificity interactively](https://specificity.keegan.st/)). This means that in the element`<div class="col-md-4 myclass">` the bootstrap rule `.bootstraptransition .col-md-4` would override `.myclass`, regardless of load order. The solution is to also elevate every single custom rule with the transition class.

```less
.bootstraptransition {
    @import (less) "../../css/styles.css"; 
    // the `(less)` bit interprets .css as .less
}
```

The benefit of this entire approach is that it enables us to scope Bootstrap to segments of the page, thus overriding another framework that uses the same class names.

```html
<body>
    <nav class="bootstraptransition">
        <p>This content is Bootstrapped and overrides Skeleton.<p>
        <div class="container">
            ...
        </div>
    </nav>
    <section>
        <p>This content is bootstrap-free and uses Skeleton.<p>
        <div class="container">
            ...
        </div>
    <section>
</body>
```

The downside is that every single css rule is now bloated with an extra class, but gzip can probably handle the repetition (and in any case, this is the cost of running two frameworks on the same page, and an excellent reason for management to allocate enough time to transition fully to the new framework). Another downside is that we now have to manage bootstrap-skeleton overrides. Given the following CSS:

```css
/* bootstrap-transitional.css */
.bootstraptransitional .classname {
    margin: 0;
}

/* styles-transitional.css */
.classname {
    margin: 20px;
    border: 1px solid black;
}
```
the span in `<div class="bootstraptransitional"><span class="classname">Hello</span></div>` will have margin 0, but it will also have the unwanted border. To solve this problem, enter override-transitional.css. This file is loaded after both bootstrap-transitional.css and styles-transitional.css in order to "reset" only those things that need to be reset because of the existence of a second, unwanted framework. 

```css
/* override-transitional.css */
.bootstraptransitional .classname {
    border: none;
}
```

Why not just put `border: none;` in bootstrap-transitional.css? Because we are looking forward to one day ditching Skeleton altogether. Separating these rules into a new file will let us simply delete it when the transition is complete. Otherwise, we'd have to go digging in bootstrap-transitional to remove a ton of little resets that will be obsoleted in the absence of Skeleton.

So there you have it. A method for making two frameworks play nice. It works, it's in production, and it took me a month to pull it off while simultaneously handling a full load of actual development. 
