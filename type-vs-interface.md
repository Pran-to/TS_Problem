Type Alias vs Interface in TypeScript: Core Differences and When to Use Them
Introduction

TypeScript provides two powerful ways to define custom types: type aliases and interface. Both help developers describe the structure of objects and improve code readability. Although they look similar, they have some important differences.

Detailed Explanation

An interface is mainly used to define the structure of objects and classes. It supports declaration merging, meaning multiple interfaces with the same name can be combined.


interface User {
  name: string;
  age: number;
}

interface User {
  email: string;
}

const user: User = {
  name: "Rakib",
  age: 25,
  email: "rakib@example.com"
};


A type alias can define not only object structures but also unions, intersections, primitive types, tuples, and function types.


type ID = string | number;

type Admin = {
  name: string;
  role: string;
};

type Employee = Admin & {
  salary: number;
};


The main difference is that interfaces support declaration merging, while type aliases do not. Both support inheritance-like composition: interfaces use extends, whereas type aliases commonly use intersection (&).

For example:


interface Person {
  name: string;
}

interface Student extends Person {
  studentId: number;
}

Conclusion:

Use interfaces when defining object structures, especially when working with classes or extendable APIs. Choose type aliases when working with union types, intersection types, tuples, or complex type combinations. Both are useful, and the best choice depends on the requirements of your application.
