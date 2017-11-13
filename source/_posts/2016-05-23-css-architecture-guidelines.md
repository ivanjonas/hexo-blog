title: CSS Architecture Guidelines - my new challenge
tags:
  - css
  - architecture
category: Software Development
date: 2016-05-23 01:34:24
---

I've been tasked with creating "CSS Architecture Guidelines" at work. I'm very excited to work on this, both because I love CSS development and because it's an increase in responsibility and trust that my managers are extending to me. This post is a short survey of that work-in-progress; a full documentation might be forthcoming and published on GitHub (if they let me have my way).

I've written about JavaScript style before, but that is a hot arena with a lot of competing schools of thought. There's not much of the same in CSS. There's a [famous poll](https://css-tricks.com/poll-results-how-do-you-order-your-css-properties/) about how most CSS developers organize their rules; that's probably the most contentious code style issue in CSS, and I've never heard anyone argue for one over the other with the same zeal that some argue for tabs versus spaces (I suppose that's also an issue in CSS files, but CSS devs don't seem to care). 

This architecture document does not concern code style as much as how to develop good, reusable CSS and file organization. SMACSS has been hugely beneficial to me, who had never been exposed to any system of CSS development. I've learned a little bit about Atomic CSS, OOCSS, and BEM. I'm currently reading through Enduring CSS, and I plan to delve deeper into SUIT CSS next. Regarding code style, my reference documents are shorter: [Google HTML/CSS style guide](https://google.github.io/styleguide/htmlcssguide.html), [Idiomatic CSS](https://github.com/necolas/idiomatic-css), and the [CSSLint rules](https://github.com/CSSLint/csslint/wiki/Rules).

There are a bunch of things that are obviously good and fairly certain to be included in the architecture guidelines. Other things are either uncertain, or would be good but would involve refactoring our existing projects. There's a collaboration aspect to this work; I can't simply mandate architectural rules. Getting buy-in from the other developers, particularly those working on other projects, has been a good challenge to develop my soft skills. 

This is due by the end of 2016 Q2, so I have five more weeks to finalize everything. I hope to publish everything by then.
