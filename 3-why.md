# Why Learn Functional Programming in JavaScript?

JavaScript has features for functional programming:

1. First-class functions
2. Anonymous functions and concise lambda syntax
3. Closures

## What JavaScript is Missing

**Mutation** is a change to data structure that happens in-place:

```js
const foo = {
  bar: 'baz',
};

foo.bar = 'qux'; // mutation
```

Some features functional languages have, that JavaScript does not have:

1. Purity: Purity is enforced by FP languages. Expressions with side-effects are not allowed.
2. Immutability: FP languages disable mutations. Instead of mutating, expressions evaluate to new data structures.
3. Recursion: In many FP languages, recursion is the only way to iterate. No for, while, or do loops

## What JavaScript Has that Pure Functional Languages Lack

Apps ate the world, the web ate apps, and JavaScript ate the web.
