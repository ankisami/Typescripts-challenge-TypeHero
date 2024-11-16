# 🌟 Beginner Level: Literal Types Challenge

## 🧩 Challenge Overview

### The Problem Literal Types Solve

JavaScript, like most programming languages, has a concept of primitive data types such as string, number, and boolean. TypeScript, however, takes things to the next level by introducing literal data types.

Literal data types can be thought of as infinite subsets of their primitive counterparts. For example, instead of just having a `string` type, you can have a type that is a specific string like `'red'`.

### A Practical Use-Case

Literal types can be used to create a rainbow of possibilities. For instance, you can define a type `RainbowColor` that can only have one of the specified values in a union of literal strings:

```typescript
type RainbowColor = 'red' | 'orange' | 'yellow' | 'green' | 'blue' | 'indigo' | 'violet';
Then, you can use this type in a function to ensure invalid values are not passed in:

typescript
Copier le code
function pickColor(color: RainbowColor): void {
  console.log(`I choose the color ${color}!`);
}

// No error: TypeScript is happy!
pickColor('yellow');

// Error: Argument of type 'purple' is not assignable to parameter of type 'RainbowColor'.
pickColor('purple');
// ^?
By the way, did you know that purple's not in the rainbow because there's no "purple" wavelength of light? It's true. Our brains fabricate it for us to make sense of paradoxical visual inputs.

Literal Types for Returns
But wait! There's A LOT more! Literal types are useful for return values, too. Check out this code:

typescript
Copier le code
type Day = 'Monday' | 'Tuesday' | 'Wednesday' | 'Thursday' | 'Friday' | 'Saturday' | 'Sunday';

const isItPartyTime = (day: Day): 'definitely party time' | 'prolly lay low for now' => {
  switch (day) {
    case 'Friday':
    case 'Saturday':
    case 'Sunday':
      return 'definitely party time';
    default:
      return 'prolly lay low for now';
  }
};

isItPartyTime('Monday');
// ^?
The above example assumes a 4-day workweek since 4-day workweeks are observed to increase employee productivity.

Notice that you didn't have to specify the return type anywhere. TypeScript infers it for you, making the code both readable and type-safe.

Why Are Literal Types Even Necessary?
If you're thinking to yourself: "Why are literal types even necessary? Lots of languages don't have anything like this and they seem to get along just fine with primitive types like string and number and boolean."

The TL;DR is: once you pair type unions with literals, you can start discriminating inputs based on one particular literal instance of a type versus another. TypeScript suddenly becomes capable of doing some pretty amazing static analysis on your code that you could never do if all you had were primitive types. If that's unpalatable to you, there's always COBOL. Try that out instead maybe?

Solving This Challenge
In this prompt, we've talked mostly about string literals, but there are more kinds:

Number literals (including fractional numbers)
Boolean literals
Function literals
Object literals
Take a look at the tests and see if you can create some type literals that will satisfy the tests.
```
