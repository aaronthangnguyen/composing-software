# The Rise and Fall and Rise of Functional Programming (Composable Software)

## The Rise of Functional Programming

3 points that make lamda calculus special:

- Function are always anonymous. `(x, y) => x + y` is the anonymous function of `const sum = (x, y) => x + y`
- Functions in lambda calculus are always unary, meaning they only accept a single parameter. n-ary function `(x, y) => x + y` can be expressed as a unary function `x => y => x + y`. This transformation from n-ary to unary is known as **currying**
- Functions are first-class, meaning functions can be used as inputs to other functions, and functions can return functions

The classic function composition takes output from one function and uses it as the input for another function

```js
const compose = (f, g) => x => f(g(x));

const double = n => n * 2;
const inc = n => n + 1;

const transform = compose(double, inc);
transform(3); //8
```

## The Fall of Function Programming

Because of Object-oriented Programming, C++, and Java.

## The Rise of Functional Programming

Because of JavaScrfipt and its arrow function.

## Functional Programming Has Always Been Alive and Well

Lisp, Clojure, Erlang, and JavaScript.
