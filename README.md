# ts1_cp.uol
Typescript 1 - Understanding TypeScript - 2023 Edition  
  
### 1 Basics

- [1.1 Core Types](#1.1)
- [1.2 Nested Objects & Types](#1.2)

### 1 Basics

#### <a name="1.1"></a> Core Types

The core primitive types in TypeScript are ==all lowercase==!  

|           Types           |           Exemple          |           Description           |
|           :----:          |            :----:          |              :----:             |
|           number          |        1, 5.3, -10         | All numbers, no diference between integers or floats |
|           string          |      'Hi', \`hi\`, "Hi"    | All text values |
|           boolean         |         true, false        | Just these two |
|           object          |         { age: 30 }        | Any Javascript object, (type of object) are possible |
|           Array           |         [1, 2, 3, 4]       | Any Javascript array, type can be flexible or strict |
|           Tuple           |           [1, 2]           | Added by Typescript: Fixed lenght array |
|           Enum            |      enum { NEW, OLD }     | Added by Typescript: Automatically enumerated global constant identifiers |
|           Any             |              *             | Any kind of value, no specific type assignment |
  
Declaring Types
```ts
function add(n1: number, n2: number) {
  return n1 + n2;
}
```

#### <a name="1.2"></a> 1.2 Nested Objects & Types

Of course object types can also be created for nested objects.  

Let's say you have this JavaScript object:  
```ts
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
const product: {
  id: string;
  price: number;
  tags: string[];
  details: {
    title: string;
    description: string;
  }
}
```

Enum
```ts
enum Role { ADMIN, READ_ONLY, AUTHOR };

const person = {
  name: 'Gabriel',
  age: 23,
  hobbies: ['Sports', 'Cooking'],
  role: Role.ADMIN
}
```

Custom Types
```ts
type Combinable = number | string;

function combine(
  input1: Combinable,
  input2: combinable
) {
  ...
}
```

Function as Types
```ts
function add(n1: number, n2: number) {
  return n1 + n2;
}

let combineValues: (a: number, b: number) => number;
combineValues = add;

console.log(combineValues(8, 1));

```

Callback Function
```ts
function addAndHandle(n1: number, n2: number, cb: (num: number) => void) {
  const result = n1 + n2;
  cb(result);
}

addAndHandle(10, 20, (result) => {
  console.log(result);
});
```

#### <a name="1.3"></a> 1.3 Type Aliases & Object Types

Type aliases can be used to "create" your own types. You're not limited to storing union types though - you can also provide an alias to a (possibly complex) object type.  
For example:  
```ts
type User = { name: string; age: number };
const u1: User = { name: 'Max', age: 30 }; // this works! 
```
  
This allows you to avoid unnecessary repetition and manage types centrally.  
For example, you can simplify this code:  
```ts
function greet(user: { name: string; age: number }) {
  console.log('Hi, I am ' + user.name);
}

function isOlder(user: { name: string; age: number }, checkAge: number) {
  return checkAge > user.age;
}
```
To:  
```ts
type User = { name: string; age: number };
 
function greet(user: User) {
  console.log('Hi, I am ' + user.name);
}
 
function isOlder(user: User, checkAge: number) {
  return checkAge > user.age;
}
```
