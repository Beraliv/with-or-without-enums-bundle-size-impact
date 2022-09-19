# Bundle size impact for different solutions

The whole article – [With or without enums in TypeScript](https://blog.beraliv.dev/2022-09-10-with-or-without-enums)

## Comparison

| Approach             | Enum | Const enum | Const enum + `preserveConstEnums` | Object + `as const` | Union type |
| :------------------- | :--- | :--------- | :-------------------------------- | :------------------ | :--------- |
| Numeric values       | 126  | 44         | 112                               | 80                  | 44         |
| Heterogeneous values | 124  | 48         | 117                               | 83                  | 48         |
| String values        | 116  | 49         | 108                               | 83                  | 49         |

When you need to keep lookup object (enum, const enum + `preserveConstEnums` and object + `as const`), the optimal solution is always an object + `as const`.

When you don't need a lookup object (const enum and union type), both const enum and union type are optimal.

## Way to compare

1. [TypeScript Playground](https://www.typescriptlang.org/play) to get JS output

1. [size-limit](https://github.com/ai/size-limit) to calculate the size of each JS files

## Examples

Enums:

1. [Numeric enum](/numeric-enum.js)
1. [Heterogeneous enum](/heterogeneous-enum.js)
1. [String enum](/string-enum.js)

Const enums:

1. [Numeric const enum](./numeric-const-enum.js)
1. [Heterogeneous const enum](./heterogeneous-const-enum.js)
1. [String const enum](./string-const-enum.js)

Const enums + enabled `preserveConstEnums`:

1. [Numeric const enum](./numeric-const-enum-preserveConstEnums.js)
1. [Heterogeneous const enum](./heterogeneous-const-enum-preserveConstEnums.js)
1. [String const enum](./string-const-enum-preserveConstEnums.js)

Objects + `as const`:

1. [Numeric object + `as const`](./numeric-obj-as-const.js)
1. [Heterogeneous object + `as const`](./heterogeneous-obj-as-const.js)
1. [String object + `as const`](./string-obj-as-const.js)

Union types:

1. [Numeric union type](./numeric-union.js)
1. [Heterogeneous union type](./heterogeneous-union.js)
1. [String union type](./string-union.js)
