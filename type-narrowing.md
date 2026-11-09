Type Narrowing in TypeScript: Understanding typeof, instanceof, and the in Operator
Introduction

Type Narrowing is a TypeScript feature that allows developers to reduce a variable's possible types within a specific code block. It helps TypeScript understand the exact type of a value before performing operations. This improves type safety and prevents runtime errors.

Detailed Explanation

There are several ways to perform type narrowing in TypeScript.

1. Using typeof

The typeof operator checks primitive types such as string, number, and boolean. TypeScript uses the condition to narrow the variable's type.


function printValue(value: string | number): void {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}


Here, TypeScript understands that value is a string inside the first block and a number inside the second block.

2. Using instanceof

The instanceof operator checks whether an object belongs to a particular class.


class Dog {
  bark() {
    console.log("Woof!");
  }
}

class Cat {
  meow() {
    console.log("Meow!");
  }
}

function makeSound(animal: Dog | Cat) {
  if (animal instanceof Dog) {
    animal.bark();
  } else {
    animal.meow();
  }
}

3. Using the in Operator

The in operator checks whether a property exists inside an object.

type Admin = { name: string; role: string };
type User = { name: string; email: string };

function getInfo(person: Admin | User) {
  if ("role" in person) {
    console.log(person.role);
  } else {
    console.log(person.email);
  }
}

Conclusion:

Type Narrowing makes TypeScript applications safer and easier to maintain. The typeof operator is useful for primitive values, instanceof works with class instances, and the in operator helps identify object structures based on their properties. Using these techniques reduces unnecessary type assertions and improves code quality.
