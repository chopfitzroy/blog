---
title: Learning Haskell part three 🥳
description: Exploring Haskell infix functions ⚖
permalink: posts/{{ title | slug }}/index.html
date: '2021-07-04'
draft: true
tags: [functional, programming, haskell, series]
---

### Introduction 🚀

It's been a hectic couple of weeks and I haven't had nearly as much time to be working on Haskell as I would have liked. Recently I found some time to sit down and revisit Haskell but by the time I had got my head back in the correct space I had to move on again. Todays post will be quite short but it gives me an oppurtunity to talk about a cool little syntax feature of Haskell I recently discovered. The [infix](https://wiki.haskell.org/Infix_operator) operator, putting the function name between arguments since the early 90's! 😎.

### Let's see it in action 🔥

The infix operator is really just a way to rearrange the arguments of any given function into a more readable format. It does not effect the way your program runs and provides no performance loss or benefit when used.

The infix operator can only be used on what is known as a prefix function. An example of a prefix function is `mod` which is used to perform a [modulo operation](https://en.wikipedia.org/wiki/Modulo_operation) on two numbers. An exmaple of this might look like:

```hs
mod 9 3
```

Simple right? Give me the remainder of `9` when divided by `3`. To use the infix operator we must wrap the prefix function `mod` using the backtick (`` ` ``) syntax as below:

```hs
9 `mod` 3
```

Almost the same as before right? The only difference is that the left hand operand sits on the left of the function call 🤯. In an example this small it may seem trivial, but as you chain more and more logic together I have found that infix _tends_ to make things easier to follow.

Some functions in Haskell are infix functions by default, a good example of this is `+` which is used how you would expect:

```hs
3 + 6
```

But you can actually force these infix functions to behave like prefix functions by using parentheses like so:

```hs
(+) 3 6
```

Why you would do that I have no idea?!? 🤬 But that is completely valid Haskell.

### Wrapping up 🎁

Well that's it for today I am afraid! I know this post was only bite sized but this felt like a really nice language feature to highlight in isolation! Additionally a lot of the Haskell blogs I follow seem to use this syntax in excess, so it felt important to mention. It has really improved my ability to follow along now that I have a more in depth understanding of the infix operator 🙏. As always if you have any questions or want to know more feel free to reach out to me via email (found on my [Github](https://github.com/chopfitzroy)) and I will get back to you as soon as I can.