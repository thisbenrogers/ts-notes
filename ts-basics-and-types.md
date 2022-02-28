# The Basics of Types and Typescript

## Core Types

- number (ts and js)
  - no special type for integers or floats, just the number type.
- string (ts and js)
  - can be notated using '', "", ``
- boolean (ts and js)
  - true or false
  - in Typescript there are no 'truthy' or 'falsy' values

To avoid type coercion, we can cast a type to any core type, like so:

``` typescript
function add(n1: number, n2: number) {
  return n1 + n2;
}
```

Typescript will return errors if we try to assign an incorrect type to a value or parameter.

<br />

## Important!

Typescript's type system only helps during the development process, or before the ts code gets compiled to Javascript. This is intentional, and acts as a sanity check.

Typescript is a statically typed language (set during development), where Javascript is dynamically typed (resolves at runtime). In other words, Javascript allows type coercion, and typescript does not.

<br />

## Type assignment or inference

We can explicitly define a type, such as in the function parameters above. Specifically in functions, we _must_ assign a type, so that anything outside of the function that calls the function will be directed to use the specific type. We don't always need to be so explicit though.

With variables, we don't need to declare the type, as Typescript will infer that type from the variable definition.

Typescript knows that:

```typescript
let number = 1
```

means that ```number``` will always be a number, even if we reassign a different number to it. If we try to assign a different type to it such as ```string```, however, typescript will throw an error since we initially declared the variable as a ```number```

Similarly, typescript knows that:

```typescript
const number = 5
```

means that not only will the value of ```number``` always be a number, but that it will always be ```5``` (since we declared it as a constant)

That being said, explicitly defining a type to a variable is allowed:

```typescript
let str: string = "Wowee"
```

but it is discouraged, since it is redundant.

Now, if we create a variable but don't initialize it with a value, we absolutely _should_ assign it a type:

```typescript
let bool: boolean;
```

This is the main job of Typescript, checking types, and letting us know if we are using them incorrectly.