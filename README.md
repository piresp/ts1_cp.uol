# ts1_cp.uol
Typescript 1 - Understanding TypeScript - 2023 Edition  
  
### 1 Basics

- [1.1 Core Types](#1.1)
- [1.2 Constants](#1.2)

### 1 Basics

<a name="1.1"></a>

#### 1.1 Core Types  

The core primitive types in TypeScript are ==all lowercase==!  

| Types       | Description         |
|    :----:   |         :----:      |
| number      | 1, 5.3, -10         |
| string      | 'Hi', \`hi\`, "Hi"  |
| boolean     | true, false         |  
  
Declaring Types
```ts
function add(n1: number, n2: number) {
  return n1 + n2;
}
```