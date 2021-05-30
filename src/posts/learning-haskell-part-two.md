---
title: Learning Haskell Part Two 🎉
description: Learning the ins and outs of lists in Haskell
permalink: posts/{{ title | slug }}/index.html
date: '2021-05-30'
draft: true,
tags: [functional, programming, haskell, series]
---

### Fizz, Buzz, F***! 🤬

Today I started learning about [lists](https://wiki.haskell.org/How_to_work_on_lists) in [Haskell](https://www.haskell.org/) and while they were more or less straight forward I did run into some issues when trying to understand [list comprehension](https://wiki.haskell.org/List_comprehension) which basically allows a develoepr to perform some sort logic across each item in a list, a very basic example like so:

```hs
[x*2 | x <- [1..10]]  
-- Output: [2,4,6,8,10,12,14,16,18,20]  
```

Now I saw this as a great oppurunity to try and implement the classic [FizzBuzz](https://www.tomdalling.com/blog/software-design/fizzbuzz-in-too-much-detail/) challenge and promptly went down the rabit hole... 🐰

### Errors Everywhere...

My first implementation looked something like the below code and I used `[ fizzBuzz | current <- [1..100]]` to run:

```hs
fizzBuzz :: Int -> Either Int String
fizzBuzz current 
    | mod current 5 == 0 && mod current 3 == 0 = Right "FizzBuzz"
    | mod current 5 == 0 = Right "Buzz"
    | mod current 3 == 0 = Right "Fizz"
    | otherwise = Left current 
```

Now there is a lot to unpack there and most of this I found fumbling through google.
```hs
fizzBuzz :: Int -> Either Int String
```
Denotes the function signature and basically says that the function recieves an `Int` and will return either an `Int` or a `String`.

The `|` syntax is a way to define [guards](https://www.futurelearn.com/info/courses/functional-programming-haskell/0/steps/27226) which feel similar to switch statements in other languages, and the `Left` and `Right` syntax is required when using `Either` to say which side of the `Either` this value should be checked against.

When running this I recieved the following error:

```
• No instance for (Show (Int -> Either Int String))
    arising from a use of ‘print’
    (maybe you haven't applied a function to enough arguments?)
• In a stmt of an interactive GHCi command: print it
```

After doing a bit of research this looks to be related to the `GHCi` prompt itself and how it displays values, and while there were a few suggestions nothing I tried worked so I moved onto something else (if anyone knows how to resolve this please reach out).

Next I tried changing the command I was using to evaluate the list and print each iteration line by line using `mapM_ putStrLn $ map fizzBuzz [1..100]`, but unfortnately that rendered the following error:

```
• Couldn't match type ‘Either Int String’ with ‘[Char]’
    Expected type: [String]
    Actual type: [Either Int String]
• In the second argument of ‘($)’, namely ‘map fizzBuzz [1 .. 100]’
    In the expression: mapM_ putStrLn $ map fizzBuzz [1 .. 100]
    In an equation for ‘it’:
        it = mapM_ putStrLn $ map fizzBuzz [1 .. 100]
```

Which is fairly self explanatory essentially `putStrLn` expects `String` and I was supplying an `Int` or a `String` 🤦‍♂️.

With this new knowledge I abandoned the idea of `Either` altogether and tried casting the `Int` as a `String` using `show`, and wound up with the following implementation.

```hs
fizzBuzz :: Int -> String
fizzBuzz current 
    | mod current 5 == 0 && mod current 3 == 0 = "FizzBuzz"
    | mod current 5 == 0 = "Buzz"
    | mod current 3 == 0 = "Fizz"
    | otherwise = show current 
```

So very similar to before minus the use of `Either` and casting the final value as a `String` via `show` if needed. And Voilà everything worked as expected 🥳! now this might seem super trivial and I am aware that I have duplicate code, but this simple experiment took well over an hour to implement and there were lots of learnings along the way.

### Takeaway 🍜

I got excited and tried to jumped straight into [FizzBuzz](https://www.tomdalling.com/blog/software-design/fizzbuzz-in-too-much-detail/) before I had learnt about type signatures or `Either` or even how `GHCi` printed values to the console and I paid for it. Now I learnt loads a long the way and I don't mind this sort of haphazard approach as it helps me to better retain information and challenges my way of thinking. However if you are just starting out I recommend sticking to the order of whatever resource you are using as it doesn't take much to find yourself completely overwhelmed by concepts... 🤯

### Wrapping up 🎁

A bit more to say today and certainly more code to show for it, I will try to keep posts no longer than this in the future and make a point of tackling one topic at a time! As always if you have any questions or want to know more feel free to reach out to me via email (found on my [Github](https://github.com/chopfitzroy)) and I will get back to you as soon as I can.





