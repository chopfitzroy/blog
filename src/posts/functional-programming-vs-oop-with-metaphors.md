---
title: Functional versus object orientated
description: Functional versus object orientated, but with cheesy metaphors to keep everyone happy 😅
permalink: posts/{{ title | slug }}/index.html
date: "2021-06-01"
draft: true
tags: [functional, programming, javascript, feature]
---

### Functional vs. Object Orientated 🏹

Now I want to be clear I am not trying to start a flame war 🔥 becuase if I was I would loose, there are far more people inclined to object orientated programming that there are functional. I am just here to address some common complaints I get from people and talk about how you can get around them 💪.

The two most common complaints I recieve when trying to convince people to try out a more functional approach is inheritence and state management, which makes total sense those concepts are baked into object orientated programming and there functional counterparts are not immediately obvious 🙄.

### Inheritence 💰

So lets look at a common example of inheritence using [Typescript](https://www.typescriptlang.org/):

```ts
class Animal {
  constructor(public readonly name: string) {}

  public speak() {
    return `${this.name} makes a noise.`;
  }
}

class Dog extends Animal {
  constructor(public readonly name: string) {
    super(name);
  }

  public speak() {
    return `${this.name} barks.`;
  }
}

const animal = new Animal("Spot");
const dog = new Dog("Lucky");

console.log(animal.speak());
console.log(dog.speak());
```

The above is fairly straight forward and easy to follow right? It makes creating new _animals_ fairly simple by extending the `Animal` class each time.

Now let's look at the functional equivalent:

```ts
const makeAnimal = (speak?: (name: string) => string) => (name: string) => {
  if (speak)
    return {
      speak: () => speak(name)
    };

  return {
    speak: () => `${name} makes a noise.`
  };
};

const makeUnkown = makeAnimal();
const makeDog = makeAnimal((name: string) => `${name} barks.`);

const animal = makeUnkown("Spot");
const dog = makeDog("Lucky");

console.log(animal.speak());
console.log(dog.speak());
```

Probably not as easy to read right? Also not that much shorter in terms of lines of code... So what's the big deal? An example this contrived makes it difficult to immediately show the value of functional programming, however imagine your requirements scaling up, suddenly you want the ability to be able to create a `cat` a `mouse` a `hedgehog` 🦔, now there is a lot more boilerplate when using the object orientated approach whereas the functional approach will remain relatively terse.

But that's not all, what about composability, take this line for example:

```ts
const makeDog = makeAnimal((name: string) => `${name} barks.`);
```

Here `makeAnimal` recieves a function, what's stoping you from extracting that out to sit in isolation? Now it can be:

```ts
const bark = (name: string) => `${name} barks.`;
const makeDog = makeAnimal(bark);
```

I know I know, your thinking wait I can do that with an object orientated approach to:

```ts
const bark = (name: string) => `${name} barks.`;

class Dog extends Animal {
  constructor(public readonly name: string) {
    super(name);
  }

  public speak() {
    return bark(this.name);
  }
}
```

And to be fair you can, but because you require a refernce to `this` in order to be able to access your `name` variable the above example suddenly becomes not quite as succinct as its functional counterpart.

Ultimately it is hard to show the value of functional programming in these smaller more trivial examples, especially because of how well object orientated exceels when used in isolation, but trust me once things start to scale up functional proves to be a much more composable and lightweight experience, not to mention a much simpler mental model to follow, once you get used to it 😅.

**NOTE:** For the sake of simplicity I am intentionally not typing the return types of these functions, in a real world application I would encourage you to type function return values as well as arguments.

### State management ⚡

The elephant 🐘 in the room, state management! This has to be the number one thing I hear when talking to people about functional programming, "how can I keep state if everything is a pure function?" and to be fair the answer isn't one most people want to hear... Recursion.

Wait, wait, wait! It's not as bad as it sounds, recursion doesn't just have to be used for handling the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number) it can be used for useful things to, see the below example:

```ts
class Bottle {
    constructor(public liquid: number) { }

    public get remaining() {
        return this.liquid;
    }

    public gulp(thirst: number) {
        this.liquid = Math.max(0, this.liquid - thirst);
    }
}

const coke = new Bottle(100);
coke.gulp(50);

console.log(coke.remaining)
```

Excuse the variable names, but I've got to have some fun somewhere! 🙄 So that's probably looking fairly straight forward yes? The `Bottle` instance internally keeps track of it's `liquid` and you can check the `remaining` values if you ever want to know what is left. Awesome! Now let's looks at the functional equivalent:

```ts
const makeBottle = (liquid: number) => {
    return {
        remaining: liquid,
        gulp: (thirst: number) => makeBottle(Math.max(0, liquid - thirst))
    }
}

const coke = makeBottle(100);
const gulpedCoke = coke.gulp(50);

console.log(gulpedCoke.remaining);
```

Okay so this one might hurt your head abit, everytime we `gulp` we get a new instance of the bottle? So what's the big deal this time? As far as I'm concerned there is only one major advantage here when using a functional approach versus a more object orientated one and that is visibility. What would happen if I were to ask you what the bottle had lookled like three `gulp`'s ago? With the functional approach it's easy because you have a snapshot of the bottle returned after every `gulp`, but with the object orientated approach you have no idea, once the internal `liquid` is modified it's previous state is lost forever... Now of course if you don't store the returned bottle appropiately or override it my point is effectively redundant but you get the idea 🤯.

As far as state management goes you can see it is absolutely achievable using a functional approach you just have to tweak your mental model a bit, I would even go as far as to say the way one manages state using a functional approach is superior to that of an object orientated approach, but that really is asking to start a flame war... 🔥

### Mindset 🧠

I am of the personal opinion that the reason we like object orientated so much more than functional is because it's a model much closer to how people actually think and take in the world. For example if you were to have a gulp of coke and actually think about what the effect of that gulp was most people would say they have the same bottle of coke now with less liquid i.e object orientated. Conversely if you were to think about the same scenario with a functional mindset you would essentially say you now have a new bottle of coke that has an exact amount of liquid different from before.

### Wrapping up 🎁

Phew! Today's post carried on much more than I intended it to but I just have so much to say! Hopefully you have found this helpful and if you are having trouble with a problem and you think that it is simply impossible to do with any approach other than object orientated send me a message via email (found on my [Github](https://github.com/chopfitzroy)) and I'll see what I can do!