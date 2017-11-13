title: Alpha release of MemoryTyper - Lessons Learned
tags:
  - devops
  - lessons learned
  - tools
date: 2015-10-12 06:08:13
category: Projects
---


I never coded as hard as I did when I announced to my friends on a particular Tuesday that I would release a beta version of MemoryTyper. The pressure forced me to code with urgency like I had never before. When I technically missed the deadline, I went to sleep, woke up, and casually finished coding before releasing at 2pm the next day. The urgency of the deadline made all the difference. 

So that's one lesson (re)learned. If I have goals, I *must* put deadlines on them, or else I'll just "get around to it some day."

Also because of the pressure, I very nearly followed through on my commitment to Just Code and get the basic functionality completed. Very nearly&mdash;I spent a significant amound of time on build tooling.

<!-- more -->

(In case you don't know, *build tools* are programs that help you package up your application. If programming is buing holiday gifts for your family, build tools are the people in the store that will wrap it up professionally without you having to do it all with your own gift wrap, tape, bows, and time. Except imagine if the shopping season came around every 5 minutes. Basically, build tools automate some really monotonous stuff that you **have** to do.)

Several months ago I read and loved [http://blog.keithcirkel.co.uk/why-we-should-stop-using-grunt/](Keith Cirkel's excellent article) denouncing the use of, and the perceived need for, task runners/build tools like Gulp and Grunt. I bookmarked the follow-up article [http://blog.keithcirkel.co.uk/how-to-use-npm-as-a-build-tool/](How to Use npm as a Build Tool) for when the time came to make my own tools. And I felt, three days before my deadline, that the time had come. I couldn't stand doing things manually now that I knew firsthand the problem that is solved by build tools. 

Here's a Gist showing my current scripts
{% gist jonasninja/dad33569c6281db698be %}

And here's a brief explanation of what the "start:dev" script does:
- Open up four new terminal/console processes
  1. In the first, run a script called "watch"
    - The "watch" script in turn runs the script "build" whenever any files inside `src/` change
      - The "build" script in turn runs two commands sequentially:
        1. Bundle up the JavaScript files and put the result in `dist/js/`
        2. copy the HTML and CSS files from their directories to `dist`, maintaining their respective directory hierarchies
  2. In the second, run a script called "server:dev"
    - That script runs a simple local server that serves the files we just copied on localhost (it's like a server, but on your own computer).
  3. In the third, run a script called "open:dev"
    - That script is the simplest. It just opens your browser to the url "localhost:9090", which is where that server we just created is located.
  4. In the fourth, run a script called livereload. 
    - This is a special kind of server. My application is coded to listen to localhost:9091, which will send out a notification if the files in `dist/` change. If so, it will reload itself. No need to refresh the page!

So my second lesson is that I learned the value of having good build tools.
    
The final lesson: platform incompatibility is annoying. See, I am (currently) using Windows 10 to develop this app (don't kill me, ok?). But I will one day soon switch to Ubuntu (15.10 already installed on this very computer!) Problem is, these two operating systems use different commands for, say, copying files. So I had to go hunt down an application called `copyfiles` that works on both. The lesson is: try to have all your developers on one compatible platforms (such as Linux, Unix and Mac).

All in all, I spent at least 7 hours working on this tooling over three days. I frequently decided to change the tooling while developing, so `package.json` received not quite a dozen tooling-related commits. Whew!
