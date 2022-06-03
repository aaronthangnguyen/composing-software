# Composing Software: An Introduction

"Software development is the act of breaking a complex problem down into smaller problems, and composing simple soltuions to form a complete solution to the complex problem."

- What is function composition?
- What is object composition?

## Composing Functions

**Function composition** is the process of applying function to the output of another function.

```js
const g = n => n + 1;
const f = n => n * 2;

const doStuff = x => {
  const afterG = g(x);
  const afterF = f(afterG);
  return afterF;
};
```

If you are chaining, you are composing.

```js
const g = n => n + 1;
const f = n => n * 2;

const doStuffBetter = x => f(g(x));

doStuffBetter(20);
```

How to compose this?

```js
const doStuff = x => {
  const afterG = g(x);
  console.log(`after g: ${afterG}`);
  const afterF = f(afterG);
  console.log(`after f: ${afterF}`);
  return afterF;
};
```

First, make a utility function called `trace()`:

```js
const trace = label => value => {
  console.log(`${label}: ${value}`);
  return value;
};
```

Now we can use it like this:

```js
const doStuff = x => {
  const afterG = g(x);
  trace('after g')(afterG);
  const afterF = f(afterG);
  trace('after f')(afterF);
  return afterF;
};
```

Rewrite with `lodash`:

```js
import import from 'lodash/fp/flow';

const doStuffBetter = pipe(
  g,
  trace(after g),
  f,
  trace('after f')
);
```

or without using `lodash`:

```js
const pipe =
  (...fns) =>
  x =>
    fns.reduce((y, f) => f(y), x);
```

`pipe()` creates a pipeline of functions, passing the output of one function to the input of another.

Benefits to reduced complexity:

- Working memory
- Signal to noise ratio
- Surface area for bugs

## Composing Objects

"Favor object composition over class inheritance."

Primitives:

```js
const firstName = 'Claude';
const lastName = 'Debussy';
```

Composite:

```js
const fullName = {
  firstName,
  lastName,
};
```

Any time we build any non-primitive data structure, we are performing some kind of object composition.

3 object compositional relationships:

- Delgation: when object delegates property access to another object
- Acquaintance: when object knows about another object by reference
- Aggregation: when child objects form part of a parent object

We should form composite objects from small component parts, rather than inheriting all properties from an ancestor in a class hierarchy.

Inheritance causes problems:

- Tight coupling problem
- Fragile base class problem
- Inflexible hierarchy problem
- The duplication by necessity problem
- The gorilla/bana problem: "...the problem with object-oriented languages is they have got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle." ~ Joe Armstrong

## Conclusion

No matter how you write software, you should compose it well.
The essence of software development is composition.
