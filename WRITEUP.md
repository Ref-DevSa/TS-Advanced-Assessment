# TypeScript Assessment Write-up

## 1. What does a generic constraint (`K extends keyof T`) buy you over `any`?

A generic constraint makes my code safer because it only lets me use keys that actually exist on an object. If I make a spelling mistake or use a property that is not there, TypeScript shows an error before I run the program. If I use `any`, TypeScript accepts almost anything, so I might only find mistakes later when the program is running.

---

## 2. When would you use a mapped type vs a utility type like `Pick`?

I would use a mapped type when I want to change every property in a type. For example, making all properties `readonly` or allowing them to be `null`.

I would use `Pick` when I only need a few properties from an existing type. It is quicker because TypeScript already provides it, so I do not have to write my own mapped type.

---

## 3. What is the difference between `unknown` and `any`, and why is a type guard safer than a cast?

The biggest difference is that `unknown` makes me check the value before I use it, while `any` lets me do anything without checking. Because of that, `unknown` is much safer.

A type guard is safer than a cast because it actually checks what the value is before using it. A cast only tells TypeScript to trust me, even if the value is not the correct type. If I cast the wrong value, the program can still fail at runtime.

---

## 4. How does the `never` exhaustiveness check in the reducer protect you?

The `never` check helps make sure that every possible case is handled in a reducer or switch statement. If I forget to add a new case, TypeScript gives me an error during development. This helps me catch missing code early instead of finding bugs later when the application is running.
