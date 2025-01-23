# Criteria for Writing Clean Code (Dart)

## 1. Writing the Function Name
**Criteria:**
- Use descriptive, verb-based names that explain what the function does.
- Use **camelCase** for regular functions and **PascalCase** for class member functions if it aligns with the team's style.
- Avoid abbreviations unless they are well-known.

**Example:**
```dart
// Bad
double calc();

// Good
double calculateTotalPrice();
```

---

## 2. Writing the Variable Name
**Criteria:**
- Use descriptive, meaningful names that indicate the variable’s purpose.
- Use **camelCase** for variables.
- Avoid **single-character** names except for loop counters (`i`, `j`).
- Prefix boolean variables with `is`, `has`, or `can` to indicate a condition.

**Example:**
```dart
// Bad
int x;

// Good
int userAge;

// Boolean example
bool isFileLoaded;
```

---

## 3. Writing the Class Name
**Criteria:**
- Use **PascalCase** for class names.
- Class names should represent nouns or noun phrases.
- Avoid abbreviations.

**Example:**
```dart
// Bad
class usr;

// Good
class UserAccount;
```

---

## 4. Writing the File Name
**Criteria:**
- File names should be descriptive and match the primary class or functionality they represent.
- Use **snake_case** for file names.

**Example:**
```dart
// File for UserAccount class
user_account.dart
```

---

## 5. Writing the Folder Name
**Criteria:**
- Use lowercase **snake_case** for folder names.
- Group related files into folders with descriptive names.
- Avoid unnecessary nesting.

**Example:**
```dart
// Folder structure for a project
lib/
├── models/
├── controllers/
├── views/
```

---

## 6. Naming the Const Variables
**Criteria:**
- Use **UPPER_CASE** with words separated by underscores for constants.
- Prefix constants with a clear scope, e.g., `MAX_`, `DEFAULT_`, etc.

**Example:**
```dart
// Bad
const int speedLimit = 100;

// Good
const int MAX_SPEED_LIMIT = 100;
```

---

## 7. Using Comments
**Criteria:**
- Write comments to explain *why* the code exists, not *what* the code does (if the code is clear).
- Use `//` for **single-line** comments and `/* */` for multi-line comments.
- Avoid redundant comments.

**Example:**
```dart
// Bad
int speedLimit = 100; // This sets the speed limit to 100.

// Good
// MAX_SPEED_LIMIT ensures vehicles don’t exceed safe speeds.
const int MAX_SPEED_LIMIT = 100;
```

---

## 8. Keeping Code Organized
**Criteria:**
- Break code into small, reusable functions.
- Follow the Single Responsibility Principle (each function/class does one thing).
- Limit line length to 80-100 characters for readability.
- Indent consistently (e.g., 2 spaces per level for Dart).

**Example:**
```dart
// Bad
void processOrder() {
    // Handles inventory, billing, and notifications all at once.
}

// Good
void processOrder() {
    updateInventory();
    generateInvoice();
    sendNotification();
}
```

---

## 9. Consistent Indentation and Braces
**Criteria:**
- Use consistent indentation (2 spaces per level is common in Dart).
- Always use braces, even for **single-line** statements, to improve readability.

**Example:**
```dart
// Bad
if (isUserLoggedIn) return;

// Good
if (isUserLoggedIn) {
  return;
}
```

---

## 10. Avoiding Magic Numbers
**Criteria:**
- Replace "magic numbers" (unexplained literals) with named constants.

**Example:**
```dart
// Bad
if (userAge > 18) {
  // Allow access
}

// Good
const int MINIMUM_AGE = 18;
if (userAge > MINIMUM_AGE) {
  // Allow access
}
```

---

## 11. Exception Handling
**Criteria:**
- Use descriptive exception names.
- Catch exceptions only where you can handle them.

**Example:**
```dart
// Bad
try {
  // Code
} catch (e) {
  // Catch all exceptions with no context
}

// Good
try {
  // Code
} catch (e) {
  print("Error: ${e.toString()}");
}
```
