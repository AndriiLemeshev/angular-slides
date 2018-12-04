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

## Different with ECMA Script

- naming
- types, tuples and enums
- exports and imports
- lambda functions
- classes, interfaces and inheritances
- most needed features
---

TypeScript
===

## Different with ECMA Script
#### Naming

```ts
some-thing.ts // some plain class or interface
some.service.ts // some special class like sirvice, etc...
index.ts // reserved name
````
---

TypeScript
===

## Different with ECMA Script
#### Types, tuples and enums
---

TypeScript
===

## Different with ECMA Script
#### Variable and constants definition

Syntax

```ts
let variable: number = 1;
const constant: boolean = false;
````
---

TypeScript
===

## Different with ECMA Script
#### Variable and constants definition

Syntax

```ts
var a = 1; // Deprecated by me
````
---

TypeScript
===

## Different with ECMA Script
#### Basic types

- any
- boolean
- number
- string
---

TypeScript
===

## Different with ECMA Script
#### Arrays

Syntax

```ts
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
````
---

TypeScript
===

## Different with ECMA Script
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

## Different with ECMA Script
#### Tuples

Syntax

```ts
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error
````
---

TypeScript
===

## Different with ECMA Script
#### Enums

Syntax

```ts
// By default Num.Zero = 0, Num.One = 1, Num.Two = 2
enum Num { Zero, One, Two }

// Allowed only primitive constants 
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;
````
---

TypeScript
===

## Different with ECMA Script
#### Exports and imports
---

TypeScript
===

## Different with ECMA Script
#### Exports

Syntax

```ts
export const a = 1;
export let b = 2;
export function f1() { }
export class C1 { }
````
---

TypeScript
===

## Different with ECMA Script
#### Imports

Syntax

```ts
import * as m from "SomeModule";
import * from "SomeModule";
import { some } from "SomeModule";
````
---

TypeScript
===

## Different with ECMA Script
#### index.ts - file for export some from directory

Syntax

```ts
export * from './some';
export * from './some-other';
````
---

TypeScript
===

## Different with ECMA Script
#### Lambda functions
---

TypeScript
===

## Different with ECMA Script
#### Functions syntax

```ts
function f1(a) { return a; }
const f2 = (a) => a;
let f3 = (a) => { return a; };
````
---

TypeScript
===

## Different with ECMA Script
#### Functions syntax

```ts
const f1 = (a: number, b: number) => a + b;

// a - default value, b - non mandatory
const f2 = (a: number = 1, b?: number) => a + (b ? b : 0);

f1(1, 2); // 3
f2(); // 1
````
---

TypeScript
===

## Different with ECMA Script
#### Classes, interfaces and inheritances
---

TypeScript
===

## Different with ECMA Script
#### Class definition

Syntax

```ts
class C1<T> {
    private static a: number;
    protected readonly b: string;
    public c: boolean;
    e: any = 1;
    d: T; // generic
    
    constructor(argument: number,
        private field: string,
        nonMandatory?: boolean) { }
}

let obj: C1<number> = new C1(1, '2');
````
---

TypeScript
===

## Different with ECMA Script
#### Interface definition

Syntax

```ts
interface ClassInterface { method() }
interface ObjInterface { a: number }
interface FuncInterface { (a: number): string }

let a: ObjInterface = { a: 1 };
const f: FuncInterface = (a: number): string => '' + a;
````
---

TypeScript
===

## Different with ECMA Script
#### Inheritance

Syntax

```ts
abstract class AbstractClass { abstract af(); }
interface Interface1 { intf(); }
class ConcreteClass extends AbstractClass
                    implements Interface1 {
    af() { return 1; }
    intf() { return 'test' }
}

let obj: ConcreteClass = new ConcreteClass();
````
---

TypeScript
===

## Different with ECMA Script
#### Getters and setters

```ts
class C1 {
    private _a: string;
    get a(): string { return 'Value: ' + this._a; }
    set a(newA: string) { this._a = newA; }
}

let obj: C1 = new C1();
obj.a = 'test';
console.log(obj.a); // Value: test
````
---

TypeScript
===

## Different with ECMA Script
#### Most needed features
---

TypeScript
===

## Different with ECMA Script
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

## Different with ECMA Script
#### 'this' in TypeScript

```ts
class Foo {
  x = 3;
  print() { console.log('x is ' + this.x); }
}

var f = new Foo();
f.print(); // Prints 'x is 3' as expected

// Use the class method in an object literal
var z = { x: 10, p: f.print };
z.p(); // Prints 'x is 10'

var p = z.p;
p(); // Prints 'x is undefined'
````
---


TypeScript
===

## Different with ECMA Script
#### 'this' in TypeScript (fixes)

Use Instance Functions

```ts
class MyClass {
    private status = "blah";
    
    public run = () => { // <-- note syntax here
        alert(this.status);
    }
}
var x = new MyClass();
$(document).ready(x.run);
````
---


TypeScript
===

## Different with ECMA Script
#### 'this' in TypeScript (fixes)

Local Fat Arrow

```ts
var x = new SomeClass();
someCallback((n, m) => x.doSomething(n, m));
````
---


TypeScript
===

## Different with ECMA Script
#### 'this' in TypeScript (fixes)

Function.bind

```ts
var x = new SomeClass();
window.setTimeout(x.someMethod.bind(x), 100);
````
---


TypeScript
===

## The end