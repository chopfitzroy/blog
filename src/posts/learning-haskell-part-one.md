---
title: Learning Haskell Part One 🔨
description: The first in a series about my personal journey learning Haskell.
permalink: posts/{{ title | slug }}/index.html
date: '2021-05-29'
tags: [functional, programming, haskell, series]
---

### Introduction 🚀

For a long time I have been interested in functional concepts such as immutable data and pure functions and what they can do to help the developer experience when developing for the front end. As my career has progressed and my use of these concepts has increased I have found the benefit of implementing them to be unparalleled, as a result I want to dive even deeper into what functional programming is, and what better way to do that than with [Haskell](https://www.haskell.org/) 🤯.

Before going any further I would like to thank [Miran Lipovača](https://www.oreilly.com/pub/au/5027) for writing [Learn you a Haskell for Great Good!](http://learnyouahaskell.com/) which has been an invaluable resource while learning.

### History 📜

For those of you who don't know [Haskell](https://www.haskell.org/) is a language with strong roots in academia which has built a community that is both open to exploration and change. This can result in breaking changes and even [halirious bugs](https://gitlab.haskell.org/ghc/ghc/-/issues/163) 😂 but has also allowed the language to avoid some of the anti patterns seen in other mainstream languages. Anti patterns that are unable to be properly addressed given the flow on effect a change like this could have.

One of the original authors of [Haskell](https://www.haskell.org/) [Simon Peyton-Jones](https://www.microsoft.com/en-us/research/people/simonpj/) gave a wonderful [talk on Haskell](https://www.youtube.com/watch?v=re96UgMk6GQ) that does a good job of explaining the projects history and what problems it is trying to solve.

### Show me the F***ing Code 🤬

Alright alright, I know a lot of developers aren't interested in the history of projects like this, but I needed somewhere to put all those links! 😉

[Haskell](https://www.haskell.org/) is probably the closest thing we have to a language that allows us to define functionality as mathmatical expressions, and while there is some syntax that is more akin to traditional programming languages I personally find the [Haskell](https://www.haskell.org/) syntax incredibly terse. 🌴

Below is an example of declaring a simple `doubleValue` function which takes an argument `value` and returns that argument multuplied by two. It then goes on to declare another function which will double any value less than `100`, this is a good example of how [Haskell](https://www.haskell.org/) embraces [function composition](https://en.wikipedia.org/wiki/Function_composition_(computer_science)) to declare small bits of functionality and compose these to create more complex functionality.

```hs
doubleValue value = value * 2

doubleSmallValue value = if value > 100
  then value
  else doubleValue value
```

If statements in [Haskell](https://www.haskell.org/) must always contain an `else`, because all functions in [Haskell](https://www.haskell.org/) are [pure functions](https://en.wikipedia.org/wiki/Pure_function) they must **always** return a result.

### Wrapping up 🎁

That's it for today, I am only just staring my [Haskell](https://www.haskell.org/) journey and want to make a point of posting bite sized chunks regularily as opposed to big mind numbing 🥶 stories once in a blue moon! If you have any questions or want to know more feel free to reach out to me via email (found on my [Github](https://github.com/chopfitzroy)) and I will get back to you as soon as I can.

