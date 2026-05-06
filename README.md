# TypeScript Problem Solving Assignment

## Introduction

This repository contains solutions to several TypeScript problems. Each problem focuses on a core TypeScript concept such as arrays, functions, type narrowing, generics, interfaces, classes, and object-oriented programming.

## Problems Covered

- Filter even numbers from an array
- Reverse a string
- Check whether input is a string or number
- Get object property using generics
- Toggle book read status
- Class inheritance with `Person` and `Student`
- Find intersection between two arrays

## Solution Code

```ts
// Problem 1 solution:

type EventNumbers = Array<number>;

const filterEvenNumbers = (num: EventNumbers) => {
  let evenNum: EventNumbers = [];
  num.map((n) => {
    if (n % 2 === 0) return evenNum.push(n);
  });
  return evenNum;
};

const result1 = filterEvenNumbers([1, 2, 3, 4, 5, 6]);

// Problem 2 solution:

const reverseString = (input: string): string => {
  return input.split("").reverse().join("");
};

const result2 = reverseString("typescript");

// Problem 3 solution:

type StringOrNumber = string | number;

const checkType = (input: StringOrNumber) => {
  if (typeof input === "string") {
    return "String";
  } else if (typeof input === "number") {
    return "Number";
  }
};

const result3 = checkType(25);

// Problem 4 solution:

const getProperty = <T, K extends keyof T>(obj: T, key: K) => {
  return obj[key];
};

const user = { id: 1, name: "John Doe", age: 21 };

const result4 = getProperty(user, "name");

// Problem 5 solution:

interface Book {
  title: string;
  author: string;
  publishedYear: number;
  isRead?: boolean;
}

const myBook: Book = {
  title: "TypeScript Guide",
  author: "Jane Doe",
  publishedYear: 2024,
};

const toggleReadStatus = (bookObj: Book) => {
  return { ...bookObj, isRead: true };
};

const result5 = toggleReadStatus(myBook);

// Problem 6 solution:

class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

class Student extends Person {
  grade: string;

  constructor(name: string, age: number, grade: string) {
    super(name, age);
    this.grade = grade;
  }

  getDetails(): string {
    return `Name: ${this.name}, Age: ${this.age}, Grade: ${this.grade} `;
  }
}

const student = new Student("Alice", 20, "A");
const result6 = student.getDetails();

// Problem 7 solution:

const getIntersection = (arr1: number[], arr2: number[]): number[] => {
  return arr1.filter((item) => arr2.includes(item));
};

const result7 = getIntersection([1, 2, 3, 4, 5], [3, 4, 5, 6, 7]);
```

## How to Run

Install dependencies:

```bash
npm install
```

Run the TypeScript file:

```bash
ts-node index.ts
```

## Conclusion

These exercises demonstrate practical TypeScript fundamentals including type safety, reusable generic functions, interfaces, and class-based design.
