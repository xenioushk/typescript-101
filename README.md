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

```typescript
let id: number = 3
let company: string = "BlueWindLab"
let isOpen: boolean = true

let ids: number[] = [1, 2, 3, 4, 5, 6]
let x: any = "My Shop"
let mixedItems: any[] = ["Shop", 1, true]
```

## Example of a function

```typescript
const concatTheNumbers = (a: number, b: number): number => {
  return a + b
}

const result = concatTheNumbers(3, 4)
console.log(result) // return 7
```

## Example of Object & Interface

```typescript
interface UserInterface {
  id: number
  name: string
  age: number
  gender?: string
}

const User: UserInterface = {
  id: 123,
  name: "Mahbub",
  age: 24,
}

console.log(User.id) // print 123
console.log(User.name) // print Mahbub
console.log(User.age) // print 24
console.log(User.gender) // print undefined
```

## Example of adding method to an Interface

```typescript
// Add a method in to interface.

interface UserInterface {
  id: number
  name: string
  age: number
  gender?: string
  sayHello(message: string): string
}

const User: UserInterface = {
  id: 123,
  name: "Mahbub",
  age: 24,
  sayHello(message) {
    return `Hello ${message}`
  },
}

console.log(User.sayHello("Mahbub")) // Hello Mahbub
```

## Example of Types Union

```typescript
//  Types Union

const getTheId = (id: number | string): void => {
  console.log(`The id is ${id}`)
}

// call the function.
// You could pass 123 or abc123. Both are valid.
getTheId("10")
```

## Example of Types intersection.

```typescript
// First Type.
interface UserInfo {
  id: number
  name: string
}

// Second Type.
interface AccountInfo {
  accountId: string
  balance: number
}

// Intersect Two Interfaces.
type UserAccount = UserInfo & AccountInfo

const user: UserAccount = {
  id: 12,
  name: "ABC",
  accountId: "234-234-212",
  balance: 0,
}

// Print User Name: ABC.
console.log(`User Name: ${user.name}.`)
// Account No: 234-234-212 and balance is: 0
console.log(`Account No: ${user.accountId} and balance is: ${user.balance}`)
```

## Example of enum

```javascript
// Enum Example.

enum ApiRequestStatus {
  loading = "Loading",
  success = "Success",
}

const CallTheApi = (status: ApiRequestStatus): void => {
  if (status === ApiRequestStatus.loading) {
    console.log("Loading.")
  } else if (status === ApiRequestStatus.success) {
    console.log("Success")
  } else {
    console.log("Something is wrong!")
  }
}

CallTheApi(ApiRequestStatus.loading) // print the Loading. message
```

## Example of Generics

```javascript
// Define A StorageContainer Generics

class StorageContainer<T> {
  private contents: T[]
  constructor() {
    this.contents = []
  }
  addItem(item: T): void {
    this.contents.push(item)
  }
  getItem(index: number): T | undefined {
    return this.contents[index]
  }
}

// Initalize instances.

// User Names

const userNames = new StorageContainer<string>()
userNames.addItem("mahbub")
userNames.addItem("alam")
const firstName = userNames.getItem(0)
console.log(firstName) // print mahbub

// User Ages
const userAges = new StorageContainer<number>()
userAges.addItem(38)
userAges.addItem(33)

const age = userAges.getItem(0)
console.log(age) // print 38
```
