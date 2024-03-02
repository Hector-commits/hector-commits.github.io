---
title: JavaScript Initial
date: 2023-10-06 09:25:00 000
categories: [JavaScript]
tags: [JavaScript]
---

## JavaScript Built-in Types

| Name | Description |
|-------|--------|
| number | For numeric values. There isn't differentiation between integer and floating-point. |
| string | Text data. |
| boolean | true & false. |
| symbol | Unique constant values. |
| null | nonexistent/invalid ref. |
| undefined | For a defined variable but not initialized with value. |
| object | Compound values with its properties and values. |

### JavaScript conversions 1: number + string (which is a number). Implicit coercion type #1.

```JavaScript
let numerical = 800;
let text = "900";
let sum = numerical + text;

console.log(`var value: ${sum} & type: ${typeof sum}`);
```
```
returns: var value: 800900 & type: string
how to avoid: implicit conversion Number(var)
```

### JavaScript conversions 2: number = string (which is a number). Implicit coercion type #2.

```JavaScript
let numerical = 900;
let text = "900";
let check = numerical == text;

console.log(`var value: ${check} & type: ${typeof check}`);
```
```
returns: var value: true & type: boolean
how to avoid: implicit conversion = = = operand
```