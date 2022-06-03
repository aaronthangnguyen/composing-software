# Pure Functions

## What is a Function?

A function is a process which takes someinput, called arguments, and produces some ouput called a return value. Functions may serve the following purposes:

- **Mapping**: Produce some ouput based on given inputs. A function maps input values to output values.
- **Procedures**: A function maybe called to perform a sequence of steps. The sequence is known as a procedure, and programming in this style is known as procedural programming.
- **I/O**: Some functions exist to communicate with other parts of the system, such as the screen, storage, system logs, or network.

## Mapping

If we want **referential transparency**, we need to use pure functions.

## Pure Functions

**Pure function** is a function which:

1. Given same input, will always return same output.
2. Produces to side effects.

A function is **impure** if it makes sense to call it without using its return value.

KISS: Keep It **Stupid** Simple

## The Trouble with Shared State

"Non-determinism = parallel processing + mutable state" ~Martin Odersky, creator of Scala

JavaScript has many sources of concurrency, API I/O, event listeners, web workers, iframes, and timeouts. Combine that with shared state, and we have got a recipe for bugs.

Pure functions can help you avoid those kinds of bugs.

## Same Input, Same Output

A function is only pure if given the same input, it will always produce the same output.

A pure function must not rely on any external mutable state, because it's not deterministic or referentially transparent.

## No Side Effects

A pure function produces no side effects, which means that it can't alter any external state.

### Immutability

```js
// Impure addToCart mutates existing cart
const addToCart = (cart, item, quantity) => {
  cart.items.push({ item, quantity });
  return cart;
};

const originalCart = {
  items: [],
};

const newCart = addToCart(
  originalCart,
  {
    name: 'Digital SLR Camera',
    price: '1495',
  },
  1
);

console.log(JSON.stringlify(originalCart, undefine, 2));
```

```js
// Pure addToCart() return a new cart
const addToCart = (cart, item, quantity) => {
  return {
    ...cart,
    items: cart.items.concat([
      {
        item,
        quantity,
      },
    ]),
  };
};

const originalCart = {
  items: [],
};

const newCart = addToCart(
  originalCart,
  {
    name: 'Digital SLR Camera',
    price: '1495',
  },
  1
);

console.log(JSON.stringlify(originalCart, undefined, 2));
console.log(JSON.stringlify(newCart, undefined, 2));
```

## Conclusion

A **pure function** is a function which, given the same state, always return the same output, and has no side-effects

**Pure functions are the simplest kind of functions**. Prefer them whenever they are practical. They are deterministic, easy to understand, debug, and test.

An expression is **referentially transparent** if we can replace the expression with its corresponding value without changing the meaning of the program:

```js
const add = (x, y) => x + y;

// add(2, 3) always equals to 5 and 5 always equals to add(2, 3)
```

**Pure functions** can be used to optimize software performance.
