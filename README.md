## Arrays & Objects

**What an array is**

An array is an ordered list of values, stored in a single variable. Useful whenever you have a collection of related items instead of one single value.

```jsx
let fruits = ["apple", "banana", "mango"];
```

**Accessing array items — by index**

```jsx
console.log(fruits[0]);   // "apple" — indexing starts at 0
console.log(fruits[1]);   // "banana"
console.log(fruits[2]);   // "mango"
console.log(fruits[3]);   // undefined — doesn't exist
```

**Array length**```jsx
console.log(fruits.length);   // 3
console.log(fruits[fruits.length - 1]);   // "mango" — last item, common pattern
```

**Modifying arrays**

```jsx
fruits[1] = "grape";        // replace an item by index
fruits.push("orange");      // add to the end
fruits.pop();                // remove the last item
fruits.unshift("kiwi");     // add to the beginning
fruits.shift();              // remove the first item
```

**Useful array methods**

```jsx
let nums = [5, 3, 8, 1];

console.log(nums.indexOf(8));      // 2 — position of a value
console.log(nums.includes(3));     // true — does it exist in the array?
console.log(nums.join(", "));      // "5, 3, 8, 1" — array to string
console.log(nums.reverse());       // [1, 8, 3, 5]
console.log(nums.sort());          // sorts in place (default: as strings — careful with numbers, more on this later)
```

**Arrays can hold anything, including mixed types**```jsx
let mixed = ["text", 42, true, null];
```

Not common practice, but good to know arrays aren't restricted to one data type.

---

**What an object is**

An object stores data as **key-value pairs** — useful when values have labels/meaning, not just position (unlike an array).

```jsx
let person = {
  name: "Mohit",
  age: 22,
  isStudent: true
};
```

**Accessing object properties — two ways**

```jsx
console.log(person.name);        // dot notation — "Mohit"
console.log(person["age"]);      // bracket notation — 22
```

Dot notation is more common and readable. Bracket notation is needed when the key is stored in a variable, or has spaces/special characters.

```jsx
let key = "age";
console.log(person[key]);   // 22 — dot notation can't do this (pers
``````jsx
on.key doesn't work)
```

**Modifying objects**

```jsx
person.age = 23;             // update existing property
person.city = "Dehradun";    // add a new property
delete person.isStudent;     // remove a property
```

**Objects can contain arrays, and arrays can contain objects**

```jsx
let student = {
  name: "Riya",
  subjects: ["Math", "Science", "English"]
};

console.log(student.subjects[0]);   // "Math"

let students = [
  { name: "Mohit", age: 22 },
  { name: "Riya", age: 21 }
];

console.log(students[0].name);   // "Mohit"
```

This pattern — arrays of objects — is extremely common in real applications (a list of users, products, posts, etc.), worth getting comfortable reading and writing.

**Checking if a property exists**

```jsx
console.log("name" in person);   // true
console.log(person.hasOwnProperty("age"));   // true
```

**Looping through an object**

```jsx
for (let key in person) {
  console.log(key, ":", person[key]);
}
```

**Looping through an array of objects**

```jsx
for (let student of students) {
  console.log(student.name);
}
```

**`typeof` for arrays and objects**

```jsx
console.log(typeof person);        // "object"
console.log(typeof fruits);        // "object" — arrays are technically objects too
console.log(Array.isArray(fruits)); // true — correct way to check specifically for an array
```

**Common mistakes**

- Confusing array index (`[0]`) with object key access — different data structures, different access style
- Using `person.key` when `key` is a variable — should be `person[key]` (bracket notation)
- Forgetting arrays are zero-indexed — `array[array.length]` is one past the end, always `undefined`
- Assuming `typeof someArray` returns `"array"` — it returns `"object"`, use `Array.isArray()` instead**Small practice task**

```jsx
// 1. Create an array of 5 favorite movies, log the 3rd one
// 2. Push a new movie to the array, then remove the first one
// 3. Create an object "car" with keys: brand, model, year
// 4. Log one property using dot notation, another using bracket notation
// 5. Create an array of 3 objects, each representing a student (name, marks)
// 6. Loop through the array and print "Name: __, Marks: __" for each
```# Day-26
js 6 Arrays &amp; Objects
