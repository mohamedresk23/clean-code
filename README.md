# 🧼 Introduction to Clean Code

This document summarizes the core principles of writing clean, maintainable JavaScript code without using any frameworks. It’s especially tailored for front-end developers working with **Vanilla JS**.

---

## 📌 Principles of Clean Code

### 1. ✅ Use Descriptive Variable Names

```js
// ❌ Bad:
let x = 25;

// ✅ Good:
let userAge = 25;
```

> Clear variable names improve readability and make the purpose of the value obvious.

---

### 2. 🔢 Avoid Magic Numbers

```js
// ❌ Bad:
if (userAge > 18) {
  grantAccess();
}

// ✅ Good:
const LEGAL_AGE = 18;

if (userAge > LEGAL_AGE) {
  grantAccess();
}
```

> Replacing hard-coded numbers with named constants gives context to values.

---

### 3. ✂️ Keep Functions Small and Focused

```js
// ❌ Bad:
function handleUser(name, age, isAdmin) {
  if (isAdmin) {
    console.log(`Welcome Admin ${name}`);
  } else {
    console.log(`Welcome ${name}`);
  }
}

// ✅ Good:
function greetUser(name) {
  console.log(`Welcome ${name}`);
}

function greetAdmin(name) {
  console.log(`Welcome Admin ${name}`);
}

function handleUser(name, isAdmin) {
  if (isAdmin) {
    greetAdmin(name);
  } else {
    greetUser(name);
  }
}
```

> Small, single-purpose functions are easier to test and reuse.

---

### 4. 🤪 Use Meaningful Function Names

```js
// ❌ Bad:
function doIt(a) {
  return a + 10;
}

// ✅ Good:
function addTax(price) {
  return price + 10;
}
```

> A good function name eliminates the need for extra comments.

---

### 5. 🧱 Encapsulate Conditionals

```js
// ❌ Bad:
if (age > 18 && hasLicense && !isSuspended) {
  allowDriving();
}

// ✅ Good:
function canDrive(age, hasLicense, isSuspended) {
  return age > 18 && hasLicense && !isSuspended;
}

if (canDrive(age, hasLicense, isSuspended)) {
  allowDriving();
}
```

> Encapsulation improves the readability of complex logic.

---

### 6. 🗞️ Write Comments That Explain "Why", Not "What"

```js
// ❌ Bad:
// Increment x by 1
x++;

// ✅ Good:
// Move to the next slide
currentSlide++;
```

> Don’t describe what the code does — describe why it’s doing it.

---

### 7. 🧹 Remove Unused Code

```js
// ❌ Bad:
function calculateSomething() {
  // old calculation
  // let result = value * 3;
  return value * 2;
}

// ✅ Good:
function calculateSomething() {
  return value * 2;
}
```

> Dead code clutters your files and confuses future readers (including you).

---

Happy coding! 🚀
