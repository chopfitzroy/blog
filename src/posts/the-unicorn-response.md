---
title: The Unicorn Response 🦄
description: When engineers think the problem they are solving is too complicated for traditional methodologies! 🧠
permalink: posts/{{ title | slug }}/index.html
date: "2021-06-29"
draft: true
tags: [technique, programming, feature]
---

### Introduction 🚀

Picture this; you are in a meeting. Everyone is talking over each other. No one really seems to know what is going on. But one thing is clear, your team is about to take on a challenge so unique no one could have possibly ever handled anything like this before! 🤯 Sound familiar? I don't know about you but I cannot count the number of times I have started a new project and within the first few hours the team will be talking about developing new architectural patterns to solve a problem far too unique for conventional methods.

Now don't get me wrong, there absolutely are people out there solving problems outside the realm of normal software methodologies. But there is a really good chance that whatever problems you are trying to solve at your day to day job are not so unique that they require reinventing the wheel. 🎓 I am not sure where this issue comes from. Originally I thought it was related to ego and perhaps only occured when working with developers early on in their career. However I have experienced this from all developers including those much more seasoned than myself. 🤔

When I discussed this with a colleague they coined the phrase "the unicorn response", essentially meaning that some developers respond to a problem by treating it as a unicorn. In other words, each problem is something so rare and unique that no one else could have ever encountered it before. This phrase really resonated with me so I thought it might be worth writing about the issue in more detail, and don't worry I asked my colleague for permission first! 😅

### Why this is problematic? 💢

So you might be thinking what makes this a problem? There isn't necessarily anything wrong with creating a very tailored solution right? 🤔 You might even argue that a custom solution gives you more freedom to be explicit in your resolution and  potentially allow for performance optimizations that otherwise would not be possible. All of the above is totally valid, but here are a couple of reasons why custom solutions can be a bad idea:

**Scalability**; it's difficult to know if custom solutions will scale, and while you can allocate a lot of time to try and mitigate any future bottlenecks, the reality is that you are largely operating in the un-known, it is very easy to miss something obscure until it is too late.

**Onboarding**; custom solutions have to be learnt from the ground up. Most engineers have a solid understading of more traditional methodologies. If you want to stray from the norm, be prepared for long ramp up times when onboarding new team members. Additionally you may want to prepare for harsh criticism, if your team has failed to document why their solution provides value over something more mainstream some of the more seasoned engineers may be quite vocal about there reservations.

**Velocity**; ever developed a product only to have to pivot right before launch? Yeah me to... 😔 Software development is an inherently dynamic field and it is not un-common to need to rapidly switch from one direction to the next. This is especially relevant when developing something new and innovative! One of the reasons traditional software methodologies have stood the test of time is they often allow for a relatively rapid development cycle. There is a chance that whatever homegrown solution your team have developed allows for speedy iterations, but there is a good chance it does not! 😱

### Why does this happen? 💭

So if there are so many potential pitfalls with _rolling your own_ solution why do engineers do it? I've been thinking about this a lot lately and I have noticed there seems to be a recurring theme, at least in my experience! **I believe engineers often want to develop their own solutions as an overreaction to frustrations with previous projects.** We've all experienced this right, you work on an old project, your up to your eye balls in tech debt, there is one or more _nasty_ parts of the code base that everyone avoids, sound familiar? You think to yourself _If I had designed this we wouldn't have any of these problems_, well I've got good news. You're not alone. I believe every engineer has felt like this at least once in their career. 💥

The problem is this creates a bias. Engineers become so hyper fixated on what has gone wrong in the past that they approach a problem with the primary intention of fixing their previous frustrations only. Unfortunately this means they are not looking for other problematic areas, and often their solution to fix a previous frustration will cause new frustrations somewhere else... 🤯 I think it does need to be said that as engineers we should always try to be improving on what have been problem areas in the past, it just needs to be done in such a way that we understand all the possible drawbacks of whatever new solution we propose.

### Taking a step back 😎

So now we know what the problem is, and hopefully why it happens, what do we do about it? Well I think it comes down to four simple words; **take a step back**. I have recently been pushing this message with a number of teams I work with and I have to say it has had a hugely positive impact on both the way they work and the way I manage. 🎉 So what do I mean when I say take a step back? Here are a few examples to get you started:
- You're working on a problem but the solution is starting to feel unintuitive? Take a step back, confirm you understand the problem correctly and see if the problem can be tackled using an alternate paradigm.
- You're architecting a new system and you keep having to create additional services or cron jobs to handle edge cases? Take a step back, are you using an architecture that is better suited to a different problem?
- You're constantly in meetings trying to get a client to articulate their desired application but they keep getting side tracked? Take a step back, maybe your client is a visual thinker and you will have more success getting them to explain their application as user interfaces.

So how does this apply to "the unicorn response"? Well if your team is feeling like they need to create a custom solution for the problem they are trying to solve ask them to take a step back. Revisit the problem from the top and ask what scenarios a custom solution will solve, that a more traditional methodology cannot. If they can't provide any substantial arguments ask about their concerns with whichever traditional methodology fits the problem best. If it comes down to a few key frustrations with previous projects explore these scenarios in detail and talk about their specific solutions. I have found that when you break a project down like this with your team they start to realize what they are really worried about and you are able to handle those concerns in an isolated and effecient way! 🔥

### Don't be dogmatic 🐶

Now as with anything it is important not to become dogmatic about this. I have seen teams become so obsessed with using traditional methodologies that they refuse to accept any solution that even mildly deviates from whatever rules said methodology defines. If I am being honest I am actually one of those people, and it is only recently that I have begun to understand that being a zealot about this kind of thing can be incredibly damaging for team morale. 😭

My advice, always challenge your peers on a solution that deviates from whatever methodolgy your team has agreed on, but also be able to conceed to well thought out arguments and reasoning. It is a never ending balancing act finding the middle ground between maintainable and innovative and it is important that every engineer gets to be innovative in their day to day job. 🤘

### Wrapping up 🎁

Another no code article? This is getting bad! I should be back with another _down in the weeds_ article soon but I am really enjoying writing about more high level topics at the moment. As always if you have any questions or want to know more feel free to reach out to me via email (found on my [Github](https://github.com/chopfitzroy)) and I will get back to you as soon as I can.