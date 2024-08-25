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
