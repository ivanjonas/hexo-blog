title: JavaScript code styles
tags: javascript
category: Software Development
date: 2015-11-01 21:52:39
---

There is a big debate about code style. There always has been. It's not so much a Holy War as a [Lilliputian War](http://www.gradesaver.com/gullivers-travels/q-and-a/what-conflict-led-to-the-war-between-lilliput-and-blefuscu-in-gullivers-travels-40751) (because the topic of discussion is mostly subjective, but there are certainly a few objective claims, especially about readability). There are standards that have been erected, and they have massive followings. The prevalent wisdom is the following:

- Adopt the current style used in any group project you join
- "Just pick one" if starting a new project
- The style is law. Do not break the style. Use tools to enforce the style. Make extremely rare and well-documented exceptions.

<!-- more -->

First, let's talk about the word "style." What does it mean? Fashion? Beauty? No, code is UGLY, and not meant to be admired. It's a tool. Any language (human or computer) is imperfect, and imperfectly able to accomplish its goal: communication. As a tool, then, we want the maximum effectiveness. That's what code style is about: effectiveness. Utility. Not "style" in the sense of fashion or preference.

A brief foray into the meaning of "preference." The reason *They* (every developer using this word in this context) call it "preference" is complex, but not difficult to understand. People naturally prefer consistency in all areas of life. Now, JavaScript does not come with a definitive style like some languages (Python) do. Over time, many competing styles appeared to fill that need. As a result, today we have many developers in each camp, finding that their chosen style has more readability *to them* (or other qualities of utility) simply because *they* are used to it. For example, I find that English is the best language in the world because I, personally, understand it best; someone who speaks Chinese will find that language easiest. We're both right, *subjectively*. If the whole world only spoke one language, that would practically be the best language *objectively*. 

OK, back to what code style is about. Namely, effectiveness. We want maximum effectiveness. We want to find a style that is objectively better than others so as to rally around it and be done with the whole stupid question. You can measure how effective a style is by the ease of applying the style to code. In other words, **tooling**. The first and most popular code style with terrific, universal, configuration-less tooling is the winner. 

As far as I can tell, `standard` is it. `standard` repackages eslint into a standalone package so that it takes all configuration out of a project. Of course, it does a little more than that, too. There are additional tools for auto-fixing the basic style errors, plugins for your task runners, integrators for test suites, and formatters for pretty output and other kinds of formats.

Want semicolons? Use [semistandard](https://www.npmjs.com/package/semistandard). Although you just defeated the whole point of standardization. Good job. You fiend. If you're going to be evil, why don't you go ahead and implement [doublestandard](https://www.npmjs.com/package/doublestandard)?

In learning about styles I ran across JS automatic semicolon insertion (ASI). I always knew that the language did not require semicolons but accepted them, so I used them because I come from a Java background and it feels familiar and safe. Then I ran across [this article](http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding). It walked through the technical steps of why semicolon usage should be rare, but it also made the very opinionated claim that a JS developer who does not understand the basics of what a Statement even *is* should reconsider his status as an expert.

Now, I make no claim to be an expert, but I do want to become one. This was a real kick in the rear to me: "get your stuff together." The [annotated ECMAscript 5.1 (ECMA 262) language specification](https://es5.github.io/) is now on my reading list. It's rather long, but that's no insurmountable hurdle. How does one eat an elephant?
