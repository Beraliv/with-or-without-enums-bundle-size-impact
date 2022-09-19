# Bundle size impact for different solutions

The whole article – [With or without enums in TypeScript](https://blog.beraliv.dev/2022-09-10-with-or-without-enums)

Comparison:

| Approach             | Enum | Const enum | Const enum + `preserveConstEnums` | Object + `as const` | Union type |
| :------------------- | :--- | :--------- | :-------------------------------- | :------------------ | :--------- |
| Numeric values       | 126  | 44         | 112                               | 80                  | 44         |
| Heterogeneous values | 124  | 48         | 117                               | 83                  | 48         |
| String values        | 116  | 49         | 108                               | 83                  | 49         |

When you need to keep lookup object (enum, const enum + `preserveConstEnums` and object + `as const`), the optimal solution is always an object + `as const`.

When you don't need a lookup object (const enum and union type), both const enum and union type are optimal.
