title: '> npm install self-hosted-blog'
date: 2015-09-30 17:28:06
tags: 
  - something new
category: Projects
---

Well, it turns out that creating your own blog and website is complex, but only if you don't know what you're doing. I wanted to run a site (jonas.ninja) with a blog subdomain (blog.jonas.ninja) cheaply/for free, on my own, on node.js rather than crummy old PHP*. 

I do my hosting on NearlyFreeSpeech.net. They're awesome. If you are considering a host and are willing to roll up your sleeves to do the dirty work of managing a web server, check it out. It's amazing how [mere _pennies_](https://www.nearlyfreespeech.net/services/pricing) will keep a server running for months. Anyway, I briefly considered installing WordPress, but because NFS's costs are directly related to how many resources you use, I decided to try a static blog. 

Enter [Hexo](https://hexo.io/). Let me show you how easy it is to get a blog running locally. Assuming you have node/npm installed:

```bash
npm install -g hexo-cli
mkdir mywebsite
cd mywebsite
hexo init
npm install
hexo server
```

It's basically that simple, although to deploy online there's a configuration file that should probably be edited. There's no GUI for website management. Posts are [Markdown](https://help.github.com/articles/markdown-basics/) files. You edit them in Vim or Emacs ([or, better yet, any text editor created after 1975](https://youtu.be/zqBgyRTKxfA?t=14m58s)). Tags and categories are manually typed in each post, not selected from a list, so there's the risk of making a typo. You have to remember a few other things, like the [front-matter](https://hexo.io/docs/front-matter.html) fields and formats. Most importantly (for our cheapskate needs), you have to generate your static site content with `hexo generate`. For your trouble, you have a tiny, cheap, and hackable blogging platform for your lightweight, hands-on hosting solution. 

As I shared in the previous post, I was very anxious about getting my website and blog off the ground. I decided to act in spite of my fears and just tackle the challenge head-first one day, and I found that the challenge was infinitely easier now that I knew just a little more about `node` and `npm` than the last time I tried. It's good to see that dabbling in unknown technologies gives significant return on a small investment, and not just for complete beginners but also for people like me who are experienced in some other area of technology. 

Also in keeping with what I shared in my last post, I made no effort to change the default theme and styles of the blog. I did not set up the RSS feed. There is no analytics. Comments via Disqus are not yet implemented (although I might go for [Echochamber.js](https://github.com/tessalt/echo-chamber-js) instead). My blog is up and running&mdash;that's all I need right now.

\* _I am obligated to state that PHP is a fine language, that you can certainly make quality web sites with it, and that only the finished product matters. PHP was one of the first languages I learned, and I did not learn it well. As a result, I made really crummy products with it. I've never seen high-quality PHP code, and so I tend to think of PHP as a low-quality tool for minor projects._