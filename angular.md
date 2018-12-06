# Angular for beginners

![angular](images/angular-logo.svg)

---

Three components
===

- TypeScript
- Rx.JS
- Angular
---

TypeScript
===

<img src="images/ts-logo.png" width="40%" alt="typescript" />

---

TypeScript
===

## TypeScript = New Amazing JavaScript

It is a superset of JavaScript.

---

TypeScript
===

## New key features

- compiling to JS
- naming
- types
- syntax features
- API (polyfills)
- frequent problem
---

TypeScript
===

## Compiling to JS

- source code compiling to plain JS code
- debugging TypeScript code via source mapping
---

TypeScript
===

## Naming

```bash
some-thing.ts # some plain class or interface
some.service.ts # some special class like sirvice, etc...
index.ts # reserved name
````
---

TypeScript
===

## Types

Static typing and type checking at compile time. 

- primitives:
  - boolean
  - number
  - string
  - any (default)
- arrays
- classes / interfaces
---

TypeScript
===

## Types

```ts
class C1 {
    private a: number;
    public b: string;
    c: boolean;
    
    constructor(argument: number,
        private field: string) { }
}

interface ClassInterface { method() }
interface ObjInterface { a: number }

let a: ObjInterface = { a: 1 };
````
---

TypeScript
===

## Syntax features
#### Variable declaration

```ts
let variable: number = 1;
const constant: string;
let array:boolean[];

var some; // bad style
````
---

TypeScript
===

## Syntax features
#### String definition

```ts
// Template Strings (strings that use backticks)
// String Interpolation with Template Strings
let username = 'Tyrone';
let greeting = `Hi ${username}, how are you?`;

// Multiline Strings with Template Strings
let multiline = `This is an example
of a multiline string`;
````
---

TypeScript
===

## Syntax features
#### Function definition

```ts
let add1 = (a: number) => a + 1;
let addN = (a: number, n: number) => {
  return a + n;
}

function some() {} // old syntax, bad style
````
---

TypeScript
===

## Syntax features
#### Foreach

```ts
let list = ['a', 'b', 'c'];

for (let i in list) {
   console.log(i); // "0", "1", "2",
}

for (let i of list) {
   console.log(i); // "a", "b", "c"
}
````
---

TypeScript
===

## Syntax features
#### Imports and exports

```ts
import * as m from "SomeModule";
import * from "SomeModule";
import { some } from "SomeModule";

export const a = 1;
export let b = 2;
export function f1() { }
export class C1 { }
````
---

TypeScript
===

## Syntax features
#### index.ts - file for export some from directory

Syntax

```ts
export * from './some';
export * from './some-other';
````
---

TypeScript
===

## Syntax features
#### Decorators

```ts
@SomeDecorator
someDeclaration
````
---

TypeScript
===

## API (polyfills)
#### Array methods

Syntax

```ts
let arr = [1, 2, 3]

console.log(arr.filter(x => x < 2).toString()); // [1]
console.log(arr.map(x => x + 1).toString()); // [2, 3, 4]
console.log(arr.reduce((a, b) => a + b).toString()); // 6
````
---

TypeScript
===

## Frequent problem
#### 'this' in TypeScript

```ts
class Foo {
  x = 3;
  print() { console.log('x is ' + this.x); }
}

let f = new Foo();
f.print(); // Prints 'x is 3' as expected

// Use the class method in an object literal
let z = { x: 10, p: f.print };
z.p(); // Prints 'x is 10'

let p = z.p;
p(); // Prints 'x is undefined'
````
---

TypeScript
===

## Frequent problem
#### 'this' in TypeScript (fixes)

Use Instance Functions

```ts
class MyClass {
    private status = "blah";
    
    public run = () => { // <-- note syntax here
        alert(this.status);
    }
}
let x = new MyClass();
$(document).ready(x.run);
````
---

TypeScript
===

## Frequent problem
#### 'this' in TypeScript (fixes)

Local Fat Arrow

```ts
let x = new SomeClass();
someCallback((n, m) => x.doSomething(n, m));
````
---

TypeScript
===

## Frequent problem
#### 'this' in TypeScript (fixes)

Function.bind

```ts
let x = new SomeClass();
window.setTimeout(x.someMethod.bind(x), 100);
````
---

