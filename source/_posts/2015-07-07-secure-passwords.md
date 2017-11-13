title: Secure passwords
tags:
  - security
id: 391
category: Organization
date: 2015-07-07 23:52:15
---

<div class="notice">This post was first published on my personal WordPress.com blog. It was migrated here for historical reasons (and because I am a compulsive completionist) and may have been edited from its original form and content.</div>

I remade my entire online account password strategy. It was quite a project.

I have about 170 online accounts that I care about. These range from pointless web sites that I rarely use to crucial email and bank accounts. Each has a unique password. But I haven't memorized 170 unique passwords, oh no. I'm not _that_ crazy. I have password generation algorithms that I use to create passwords. Depending on the type of site that I'm viewing, I used one of a handful of (very similar) algorithms to "generate" the password.

It was sufficient at the time. <!--more-->But the world is now more dangerous than it used to be. Security breaches happen all the time; millions of accounts are compromised at once. And you only hear of the ones that go public.

Enter the [Risk Matrix](https://en.wikipedia.org/wiki/Risk_Matrix). This is a tool used in Risk Management to describe the idea that Risk is a factor of both Likelihood and Consequence. Apropos of the topic at hand, even an extremely unlikely event can be considered risky if the consequences are catastrophic.

I realized that my password strategy had not been secure enough. If one or two of my passwords were to be compromised, an astute attacker would me able to guess the algorithms fairly easily; they would instantly gain the key to my entire digital identity. Low likelihood, extreme consequences.

I researched hacking techniques to figure out how to make the best password strategy. Of course, the best strategy is to have a unique password for everything. But that involves actually memorizing everything. I could use a password management system, but I'd rather not have a [SPOF](https://en.wikipedia.org/wiki/Single_point_of_failure). The next best alternative (as far as I can tell) is to have a very secure set of algorithms that are easy to memorize, yet hard to deduce from a set of compromised passwords. So that's what I set out to do.

It took me about 11 hours to develop them.

(I was also watching anime during that entire time. That probably had something to do with how long it took.)

For over a year I've collected information about which sites I use (that is, where I have an account), which username/email are associated with them, which SSO can be used, etc. Having generating my new algorithms, I used this list to make sure I updated all of my accounts.

(Having such a list has been extremely beneficial for me in other ways. For example, when my physical address or phone number changes, I know which accounts to update and do not forget any. I highly recommend making such a list for yourself. Just don't store any actual credentials in it!)

The end result: a tangle of characters, numbers, and symbols that make sense to me, but which a dedicated attacker would be hard-pressed to decode. Unfortunately, because the algorithms are complex, it takes me about four times longer to type in a password than before. But I suppose that's a price I'm willing to pay for security.
