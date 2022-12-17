# ts1_cp.uol
Typescript 1 - Understanding TypeScript - 2023 Edition  
  
### 1 Basics

- [1.1 Core Types](#1.1)
- [1.2 Nested Objects & Types](#1.2)

### 1 Basics

#### 1.1 Core Types {#1.1}

The core primitive types in TypeScript are ==all lowercase==!  

|           Types           |         Description        |
|           :----:          |            :----:          |
|           number          |        1, 5.3, -10         |
|           string          |      'Hi', \`hi\`, "Hi"    |
|           boolean         |         true, false        |  
|           object          |         { age: 30 }        |
  
Declaring Types
```ts
function add(n1: number, n2: number) {
  return n1 + n2;
}
```

#### 1.2 Nested Objects & Types {#1.2}

Of course object types can also be created for nested objects.  

Let's say you have this JavaScript object:  
```js
const product = {
  id: 'abc1',
  price: 12.99,
  tags: ['great-offer', 'hot-and-new'],
  details: {
    title: 'Red Carpet',
    description: 'A great carpet - almost brand-new!'
  }
}
```
  
This would be the type of such an object:  
```ts
{
  id: string;
  price: number;
  tags: string[];
  details: {
    title: string;
    description: string;
  }
}
```