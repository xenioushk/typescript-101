# TypeScript 101

## Installation

Run the following command to install TypeScript globally.

```bash
npm install -g typescript
```

## Initalization

Go to the project directory and run the following command. It will generate the tsconfig.json file.

```bash
tsc --init
```

## Compile & run the code

Create a file **index.ts** and write all the codes. However, We can not run the `.ts` file directrly. So, we need to compile `index.ts` file, and compile it to `index.js` file.

Run the following command.

**Compile the file**

```bash
tsc
```

**Run the file**

```bash
node index.js
```

## Examples of types

```bash
let id:number=3;
let company:string= "BlueWindLab";
let isOpen:boolean = true;

let ids:number[]=[1,2,3,4,5,6];
let x:any = "My Shop";
let mixedItems: any[]=["Shop", 1, true];
```

## Example of a function

```bash
const concatTheNumbers = ( a:number, b:number ):number=>{
  return a+b;
}

const result = concatTheNumbers(3,4);
console.log(result); // return 7
```

## Example of Object & Interface

```bash
interface UserInterface {
  id: number
  name: string
  age: number
  gender?: string
}

const User: UserInterface = {
  id: 123,
  name: "Mahbub",
  age: 24
}

console.log(User.id) // print 123
console.log(User.name) // print Mahbub
console.log(User.age) // print 24
console.log(User.gender) // print undefined
```
