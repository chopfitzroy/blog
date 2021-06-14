---
title: Techniques to keep code clean
description: Some of the general techniques I use to keep my code maintainable over time 🎓
permalink: posts/{{ title | slug }}/index.html
date: "2021-06-14"
tags: [technique, programming, feature]
---

### Introduction 🚀

Most developers don't like working with other people's code, but sometimes they even don't like working with their own code! Now I want to make it clear that this is not a bad thing, struggling to reason about code you wrote one year ago, one month ago, or even one week ago often means you have improved as a developer and techniques you thought were effecient then now seem dated compared to the current tools in your belt 🔨.

That being said it is inevitable that you are going to have to revisit existing code from time to time, sometimes it will be yours, sometimes it will be someone else's entirely. Knowing this, you can set your future self up for success, so you don't end up cursing yesterday you tomorrow 🤬.

### Structuring 📚

Code structuring can be difficult and often the requirements change from one project or language to another. Most popular programming languages include some sort of guidelines or code structuring principles as part of their documentation, so before you start googling, I would recommend checking the documentation for any pointers. 😈

If that doesn't work, my next recommendation would be to look at the boilerplate for any _official_ generators for the framework or language you are using and see how they have been structured, i.e [Create React App](https://reactjs.org/docs/create-a-new-react-app.html#create-react-app) or [Vue CLI](https://cli.vuejs.org/). If there are no tools like this to leverage, the next best option is to review the source code of popular libraries for the language you are working in, i.e [Numpy](https://github.com/numpy/numpy) for Python or [Express](https://github.com/expressjs/express) for Node.

If after all of that you are still struggling [Ben Awad](https://twitter.com/benawad) did actually release [Destiny](https://github.com/benawad/destiny) which is basically [Prettier](https://prettier.io/) for file structures, although I would use this at your own risk! 😅

### Responsibilities 🤏

Responsibility is an age old topic when it comes to development, and while I can make some recommendations in regards to handling this, I would encourage every developer to become familiar with these principles:

- [DRY code](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
- [WET code](https://www.deconstructconf.com/2019/dan-abramov-the-wet-codebase) (not a meme, I genuinely believe in this one 🙏)
- [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)
- [SOLID principles](https://en.wikipedia.org/wiki/KISS_principle)
- [Single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle)

As for my advice all I will say is, if a solution is starting to feel too complicated, it probably is... Whenever this happens take a step back, review any assumptions you may have made about the problem and revisit it from the top. 🚀

### Optimize for disposability 🚮

<blockquote class="twitter-tweet">
    <p lang="en" dir="ltr">My favorite programming idea came from an interview I did at Netflix early in my career:<br><br>&gt; Optimize for disposability<br><br>Everybody hates everybody&#39;s code (and their own) eventually, so just make it easy to throw it out.</p>
    &mdash; Ryan Florence (@ryanflorence)
    <a href="https://twitter.com/ryanflorence/status/1390709000224706565?ref_src=twsrc%5Etfw">May 7, 2021</a>
</blockquote>

This has got to be one of my all time favourite expressions and one I only heard recently. Now I know what you're thinking, isn't that just the same as writing code for modularity? And to an extent you're right. Disposable code and modular code have a lot in common. They are isolated, decoupled, they should be fairly easy to reason about... I hope. 🤣

How I interpret this (largely based on the original poster's additional comments) is that it puts a highlight on the scope or purpose of the code being written. Often when developers write modular code they also try to write extendable code, which by the way is a myth I plan on writing about! 😡 What I mean by this is developers often take great pains to make sure that what they write will be easy to work with at a later date (which I also am aware is what this article is trying to encourage) but sometimes that just isn't worth it.

What do you mean not worth it?!? What I mean is when a piece of code is so small and focused it might not be worth optimizing it to the point where it can be extended later. This is because extending it later will either never happen or the additional functionality requested will require such significant changes that it will be easier to throw out what is there and start again. Which is something all developers do whether we admit it or not! 😎

This can definitely be a difficult judgement call to make and I wouldn't worry about it too much if you are just starting out. However if you are a seasoned developer and you have seen this kind of thing happen before, you will be able to see the value in avoiding extendability where it is not needed and allowing disposability where it is needed. ⚡

### Wrapping up 🎁

A less technical article today! But I am glad I was able to get this written down as it will actually serve as a useful guide for myself next time I am looking at implementing a new feature or starting a new project. 🎉 If you have any questions or want to know more feel free to reach out to me via email (found on my [Github](https://github.com/chopfitzroy)) and I will get back to you as soon as I can.