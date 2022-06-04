# What is Functional Programming?

**Functional programming** is a programming paradigm where applications are composed using pure function, avoiding shared mutable state, and side-effects. Functional programming is usual more declarative than imperative, meamning that we express what to do rather than how to do it.

Concepts:

- Pure functions
- Function composition
- Avoid shared state
- Avoid mutating state
- Avoid side effects
- Declarative vs imperative

## Pure Functions

- Given same inputs, always returns same output
- Has no side-effects

## Function Composition

Function composition is the process of combining two or more fuctnions in order to produce a new function or perform some computation.

## Shared State

...

## Immutability

...

## Side Effects

...

## Reusability Through Higher Order Functions

...

## Containers, Functors, List, and Streams

A **functor data structure** is a data strucutre that can be mapped over. When we see the word functor, we should think "mappable".

## Declarative vs Imperative

- **Imperative** programs spend lines of code describing the specific steps used to achieve the desired results - the folow control: _How to do things_
- **Declarative** programs abstract the flow control process (the how gets abstracted away), and instead spend lines of code describing the data flow: _What todo do_.

```js
// Imperative
const doubleMap = numbers => {
  const doubled = [];
  for (let i = 0; i < numbers.length; i++) {
    doubled.push(numbers[i] * 2);
  }

  return doubled;
};
```

```js
// Declarative
const doubleMap = numbers => numbers.map(number => number * 2);
```

## Conclusion

Functional programming favors:

- **Pure functions** over shared state and side effects
- **Immutability** over mutable data
- **Function composition** over imperative flow control
- **Generic** utilities that act on many data types over object methods that only operate on their colocated data
- **Declarative** over imperative code (what to do, rather than how to do it)
- **Expressions** over statements
