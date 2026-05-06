# Using Pick and Omit to keep typeScript Code Dry

## Introduction

In large projects, repeating similar type definitions creates maintenance problems. TypeScript provides utility types such as Pick and Omit to create smaller slices of a master interface.

Master Interface

```
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
  role: string
}

```

## Using Pick

Pick creates a new type by selecting only specific properties.

```
type UserPreview =Pick <User, "id" | "name" | "email">

```

Useful when showing profile information without exposing everything.

## Using Omit

Omit creates a new type by removing properties.

```
type publicUser = Omit <User, "password">

```

This is useful for API responses where sensitive data should not be returned.

## Why This Prevents Duplication

Without utility types, you may rewrite similar interfaces many times.

```
interface UserPreview {
  id: number;
  name: string;
  email: string;
}

```

if the original User changes, every copied version must be updated manually.

## DRY Principle

DRY means don't repeat yourself. Pick and Omit reuse one master interface and generate specialized version from it.

This keeps code:

1. easier to maintain
2. more consistent
3. less error-prone

## Conclusion

Pick and Omit help build clean, reusable type definitions. Instead of duplicating interface, create small focused slices from one source of truth.
