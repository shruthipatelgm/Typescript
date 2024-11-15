Here’s a concise **TypeScript reference document** that covers essentials from **basic to intermediate** level:

---

# **TypeScript Cheat Sheet**

### **1. Setup**
- Install: `npm install -g typescript`
- Initialize Project: `tsc --init`
- Compile: `tsc yourFile.ts`

---

### **2. Basic Types**
```typescript
let isDone: boolean = true;
let age: number = 25;
let firstName: string = "John";
let numbers: number[] = [1, 2, 3];
let tuple: [string, number] = ["hello", 42];
```

---

### **3. Functions**
```typescript
// Function with typed parameters and return value
function add(a: number, b: number): number {
  return a + b;
}

// Optional parameter
function greet(name?: string): string {
  return `Hello, ${name || "Guest"}`;
}

// Default parameter
function multiply(a: number, b: number = 2): number {
  return a * b;
}
```

---

### **4. Interfaces**
```typescript
interface User {
  name: string;
  age: number;
  isAdmin?: boolean; // Optional property
}

const user: User = { name: "Alice", age: 30 };
```

---

### **5. Classes**
```typescript
class Person {
  private name: string;
  protected age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  greet(): string {
    return `Hello, my name is ${this.name}`;
  }
}

class Student extends Person {
  constructor(name: string, age: number, private grade: number) {
    super(name, age);
  }

  getGrade(): number {
    return this.grade;
  }
}

const student = new Student("John", 20, 95);
console.log(student.greet());
```

---

### **6. Enums**
```typescript
enum Direction {
  Up,
  Down,
  Left,
  Right,
}

let move: Direction = Direction.Up;
```

---

### **7. Generics**
```typescript
function identity<T>(value: T): T {
  return value;
}

let numberId = identity<number>(42);
let stringId = identity<string>("Hello");
```

---

### **8. Type Aliases**
```typescript
type Point = {
  x: number;
  y: number;
};

let point: Point = { x: 10, y: 20 };
```

---

### **9. Union and Intersection Types**
```typescript
// Union
let id: string | number = 123;

// Intersection
type Admin = { admin: boolean };
type User = { name: string };
type AdminUser = User & Admin;

const adminUser: AdminUser = { name: "Alice", admin: true };
```

---

### **10. Utility Types**
```typescript
interface User {
  id: number;
  name: string;
  age?: number;
}

type PartialUser = Partial<User>;  // All properties optional
type ReadonlyUser = Readonly<User>; // All properties readonly
```

---

### **11. Type Assertions**
```typescript
let someValue: unknown = "Hello World";
let strLength: number = (someValue as string).length;
```

---

### **12. Modules**
```typescript
// person.ts
export class Person {
  constructor(public name: string) {}
}

// app.ts
import { Person } from "./person";

const john = new Person("John");
```

---

### **13. Async/Await**
```typescript
async function fetchData(): Promise<string> {
  const response = await fetch("https://api.example.com");
  return response.json();
}
```

---

### **14. Advanced Types**
- **Mapped Types:**
```typescript
type Readonly<T> = {
  readonly [P in keyof T]: T[P];
};
```

- **Conditional Types:**
```typescript
type IsString<T> = T extends string ? true : false;

let result: IsString<number>; // false
```

---

This document provides a well-rounded overview of TypeScript features to get started and move towards intermediate-level concepts. Let me know if you'd like explanations or examples for any specific part!