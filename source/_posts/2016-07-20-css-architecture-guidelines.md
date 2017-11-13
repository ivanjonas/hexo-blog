title: CSS Arcitecture Guidelines
category: Software Development
tags:
  - css
  - architecture
  - success
date: 2016-07-20 12:00:00
---

Well, I did it. I finished the architectural guidelines. 

As far as I know, I'm the only one who uses it. Or is even aware of its existence. Working in isolation from the rest of the company has its benefits, but also its drawbacks.

I'm not yet an expert on front end development, so I am sure that my guide is lacking in several fronts. I suspect that the beginning is too verbose; I wrote it partly as an exercise in apologetics for explaining the benefits of such guidelines to my colleagues. The actual guidelines can be summarized very simply (and loosely in order of importance):

- Use a naming convention like that of [SUIT CSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md) or [BEM](http://getbem.com/naming/).
- Use a component methodology like [SMACSS](https://smacss.com/), [SUIT](https://github.com/suitcss/suit/blob/master/doc/README.md), or [BEM](http://getbem.com/introduction/). **This is key**
- Use selectors of specificity 0,0,1,0 (a single class selector).
- Use namespaces to separate classes based on purpose (modules, script hooks, integration testing, frameworks, state management, etc).
- Know when to break away from the component methodology. It will only help you 90% of the time.
- Document your components in a pattern library.
- Organize related CSS and JS files in the same directory, or in symmetrical directory structures.
- Order every HTML elements' attributes: `id`, `class`, and then everything else.

The full guidelines, as cringe-inducing to my future self as I'm sure they'll be, can be found [here](https://www.evernote.com/shard/s119/sh/2deb409e-e6fa-4645-baf3-a39b9cc64c9c/2c827a94ae78ba8f3d7eae5f63c9d361). I learned a lot putting this together. Not only did I learn the subject matter, but also about how difficult it can be to write good documentation on topics of a less objective nature.
