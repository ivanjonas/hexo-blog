title: Hungarian Notation is just Namespacing
tags:
  - naming things
category: Software Development
date: 2017-05-01 10:45:00
---

There are two kinds of [Hungarian Notation](https://en.wikipedia.org/wiki/Hungarian_notation). "Systems" Hungarian ascribes a _type_ to a variable, typically in a language that does not have strong typing, and "Apps" Hungarian appends to the variable name a dimension of intent. In a nutshell, one is to be avoided and the other lives on as namespacing.

If you've ever had to muck about with very old code, you may have seen variables such as `strFirstName` or `intProductCount`. I first ran across this when I was first discovering programming in VBA (yuck). It sort of made sense to my newbie mind. When I later learned Java in a college course, System Hungarian became worse than useless. The type is already enforced by the language, so `int intProductCount` is obviously redundant and creates manual work during refactoring. It is largely accepted throughout the programming community that Systems Hungarian notation is an antipattern, but it is slightly less widely known that this "bad" implementation of Hungarian notation is not what the creator envisioned at all!

Apps Hungarian, on the other hand, is the "real" Hungarian notation, and it's very good! It attempts to communicate something about the purpose of the variable. Where Apps Hungarian was meant for programming languages, it applies anywhere you need to name something. The principle applies to HTML/CSS classes, too. Consider the following code:

```html
<div class="search field space">
    <input ...>
</div>
```

You can take a guess at what those classes mean, but you probably won't be very confident! What if the classes were named like this:

```html
<div class="js-search c-field, u-space">
    <input ...>
</div>
```

With just a little knowledge of your project's conventions, you now know that `js-search` is a hook for javascript, `c-field` is the root of the "field" component, and `u-space` is a utility class for slapping on additional styles, probably just margin and/or padding. That's the benefit of Apps Hungarian. To me, Hungarian notation is nothing more than the first implementation of today's concept of *namespacing*, which is one high-impact method for promoting good CSS architecture. Perhaps there's a distinction between the two terms, but indisputably the aim of both is to communicate intent.

Here's a [twelve-year-old post](https://www.joelonsoftware.com/2005/05/11/making-wrong-code-look-wrong/) from Joel Spolsky that is both amusing and more informational than my own li'l blog post.
