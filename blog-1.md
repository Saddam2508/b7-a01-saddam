# Why any Is a Type Safety Hole and Why unknown Is Safer

## introduction:

TypeScript helps catch mistakes before code runs. But not all types give the same level of safety. Two commonly discussed types are any and unknown.

The any type disables TypeScript's checking, while unknown keeps type safety and forces validation before use.

## Why any is Called a Type Safety Hole

When a value is typed as any, TypeScript allows almost anything .

```
let value: any = "hello";
value.toUpperCase();
value.notExistingMethod()

```

TypeScript will not report an error, even if the method does not exist. This creates a "type safety hole" because invalid code can pass compilation.

## Why unknown Is Safer

unknown is useful when data comes from an unpredictable source like APIs, user input, or external files.

```
let value: unknown = "hello" ;

value.toUpperCase();

```

This produces an error because TypeScript does no know the actual type yet.

## Type Narrowing

Type narrowing means checking a value before using it so TypeScript can understand its real type.

```
let value: unknown = "hello";
if (typeof value === "string){
console.log(value.toUpperCase());
}

```

Inside the if block, TypeScript knows value is a string

## Conclusion:

any removes TypeScript's protection and can hide bugs. unknown is safer because it requires validation before usage. In real projects, unknown is the better choice when data is uncertain.
