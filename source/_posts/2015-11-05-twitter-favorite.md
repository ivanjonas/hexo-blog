title: Twitter Favorite
tags:
  - greasemonkey
  - twitter
category: Software Development
date: 2015-11-05 01:48:58
---

The following tweet perfectly describes how I feel about Twitter's switch to the generic "like" used by other social networks. 

<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/MattGertz">@MattGertz</a> An incomplete list of reasons I used favourite: <a href="https://t.co/gKS8yJDY0O">pic.twitter.com/gKS8yJDY0O</a></p>&mdash; Rob O&#39; Sullivan (@Rob0Sullivan) <a href="https://twitter.com/Rob0Sullivan/status/661729870410575873">November 4, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

The term "like" has problems that Facebook has been trying to solve. Namely, what do you do about sad posts? "So-and-so passed away last night. Please keep the family in your thoughts and prayers," for example. I really don't want the poster receiving a notification that says "Ivan likes this." I'd rather it say, "Ivan comiserates with this." I hear Facebook is testing a new way of responding to content, but it hasn't happened yet. Until then, its problems are now also Twitter's problems. 

Well, I can't change Twitter, but I can change my browser. Someone made [a Chrome plugin](https://chrome.google.com/webstore/detail/fav-forever/belacnojopafdobcknphjadpphldcpao/related) to change the heart/like back to the familiar star/favorite. I modified it a little bit and published a Greasemonkey script to do the same on Firefox:

<script src="https://gist.github.com/jonasninja/b737e5817a8e44b08939.js"></script>

There's also one for TweetDeck on Chrome (via [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?)) or Firefox, although it does not change the dog-ear "liked" because that's actually an image and I didn't feel like making and hosting a modified sprite sheet):

<script src="https://gist.github.com/jonasninja/c4367102115facb1d01d.js"></script>

To install, first [install Greasemonkey](https://addons.mozilla.org/en-us/firefox/addon/greasemonkey/). Simply copy the entire contents of the Gist above, and when you try to create a new Greasemonkey script, you'll have the option to "Use Script From Clipboard" at the bottom of the little popup. Just enable it and you're golden. It won't change how other people see your favorite/like, but you can at least delude yourself into thinking that you do not, in fact, "like" everything under the sun. And that's gotta be worth something.
