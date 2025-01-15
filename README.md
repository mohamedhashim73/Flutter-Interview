# Flutter Interview Questions
1- What is OOP | Main Principles | Examples ?

2- What is a Compile-Time Error | Runtime Error ?

3- What is a difference between Authentication | Authorization ?

### What is OOP (Object-Oriented Programming) ?

**OOP (Object-Oriented Programming)** is a programming paradigm that organizes software design around **objects** rather than functions and logic. An object is a self-contained unit that consists of:

1. **Attributes (Properties)**: Data that describes the object.
2. **Methods (Functions)**: Actions or behaviors the object can perform.

OOP is based on four main principles:

1. **Encapsulation**: Bundling data and methods that operate on that data within a single unit (object) and restricting direct access to some of the object's components.
2. **Inheritance**: Allowing a class to inherit properties and methods from another class, promoting code reuse.
3. **Polymorphism**: Allowing objects to be treated as instances of their parent class, enabling flexibility and dynamic behavior.
4. **Abstraction**: Hiding complex implementation details and exposing only the necessary features of an object.

---

### Benefits of Using OOP

1. **Code Reusability**:
   - Through inheritance, you can reuse existing code, reducing duplication and improving efficiency.
   - Example: In Flutter, you can create a base `Widget` class and extend it for specific use cases.

2. **Modularity**:
   - Objects are self-contained, making it easier to maintain and update code.
   - Example: In Flutter, you can create reusable components (widgets) like buttons, cards, etc.

3. **Scalability**:
   - OOP makes it easier to manage and scale large applications by breaking them into smaller, manageable objects.

4. **Maintainability**:
   - Encapsulation ensures that changes to one part of the code don’t affect other parts, making debugging and maintenance easier.

5. **Abstraction**:
   - Simplifies complex systems by exposing only necessary details.
   - Example: In Flutter, you don’t need to know how a `Text` widget renders text; you just use it.

6. **Polymorphism**:
   - Allows flexibility in code by enabling objects to take on multiple forms.
   - Example: In Flutter, you can use a `ListView` to display different types of widgets (text, images, etc.).

7. **Improved Collaboration**:
   - OOP makes it easier for teams to work on different parts of an application simultaneously.

---

### OOP in Flutter

As a Flutter developer, you’re already using OOP concepts extensively. Flutter is built around widgets, which are essentially objects. Here’s how OOP applies in Flutter:

1. **Widgets as Objects**:
   - Every widget in Flutter (e.g., `Container`, `Text`, `Row`, `Column`) is a class that encapsulates properties and methods.

2. **Inheritance**:
   - Flutter widgets often extend other widgets. For example, `StatelessWidget` and `StatefulWidget` are base classes that you extend to create custom widgets.

3. **Encapsulation**:
   - Widgets encapsulate their internal logic and expose only the necessary properties (e.g., `color`, `child`, `padding`).

4. **Polymorphism**:
   - You can pass different types of widgets to a `child` property, and Flutter will handle them appropriately.

5. **Abstraction**:
   - Flutter abstracts away the complexity of rendering and layout, allowing you to focus on building the UI.

---

### Example of OOP in Flutter

```dart
// Encapsulation and Abstraction
class CustomButton extends StatelessWidget {
  final String text;
  final VoidCallback onPressed;

  CustomButton({required this.text, required this.onPressed});

  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: onPressed,
      child: Text(text),
    );
  }
}

// Inheritance
class CustomIconButton extends CustomButton {
  final IconData icon;

  CustomIconButton({
    required String text,
    required VoidCallback onPressed,
    required this.icon,
  }) : super(text: text, onPressed: onPressed);

  @override
  Widget build(BuildContext context) {
    return ElevatedButton.icon(
      onPressed: onPressed,
      icon: Icon(icon),
      label: Text(text),
    );
  }
}

// Polymorphism
void main() {
  runApp(MaterialApp(
    home: Scaffold(
      body: Center(
        child: Column(
          children: [
            CustomButton(
              text: "Click Me",
              onPressed: () => print("Button Pressed!"),
            ),
            CustomIconButton(
              text: "Icon Button",
              onPressed: () => print("Icon Button Pressed!"),
              icon: Icons.star,
            ),
          ],
        ),
      ),
    ),
  ));
}
```

---

### Notes for Flutter Developers

1. **Widgets are Classes**:
   - Always think of widgets as classes and leverage OOP principles to create reusable and maintainable components.

2. **State Management**:
   - Use OOP to encapsulate state logic in classes (e.g., `ChangeNotifier`, `Provider`, `Bloc`).

3. **Custom Widgets**:
   - Create custom widgets by extending `StatelessWidget` or `StatefulWidget` to encapsulate UI logic.

4. **DRY Principle**:
   - Avoid code duplication by reusing widgets and logic through inheritance and composition.

5. **Testing**:
   - OOP makes it easier to write unit tests for individual components.

---

By embracing OOP in Flutter, you can build scalable, maintainable, and efficient applications. It’s a fundamental concept that will help you write cleaner and more organized code.

### What is a Compile-Time Error?

A **compile-time error** occurs when the code is being compiled (i.e., converted from source code to machine code). These errors are detected by the compiler before the program is executed. They usually result from syntax mistakes, type mismatches, or violations of language rules.

#### Examples of Compile-Time Errors in Dart/Flutter:

1. **Syntax Error**:
   - Missing semicolon, parenthesis, or curly braces.
   ```dart
   void main() {
     print("Hello, World") // Missing semicolon
   }
   ```
   **Error**: `Expected ';' after this.`

2. **Type Mismatch**:
   - Assigning a value of the wrong type to a variable.
   ```dart
   int number = "Hello"; // Assigning a String to an int variable
   ```
   **Error**: `A value of type 'String' can't be assigned to a variable of type 'int'.`

3. **Undefined Variable or Method**:
   - Using a variable or method that hasn't been declared.
   ```dart
   void main() {
     print(undefinedVariable); // Variable not defined
   }
   ```
   **Error**: `The name 'undefinedVariable' isn't defined.`

4. **Missing Required Arguments**:
   - Not providing required parameters to a function or constructor.
   ```dart
   void greet(String name) {
     print("Hello, $name");
   }

   void main() {
     greet(); // Missing argument
   }
   ```
   **Error**: `The argument type 'Null' can't be assigned to the parameter type 'String'.`

5. **Incorrect Widget Usage**:
   - Using a widget incorrectly in Flutter.
   ```dart
   class MyApp extends StatelessWidget {
     @override
     Widget build(BuildContext context) {
       return Scaffold(
         body: Center(
           child: Text(123), // Passing an int instead of a String
         ),
       );
     }
   }
   ```
   **Error**: `The argument type 'int' can't be assigned to the parameter type 'String'.`

---

### What is a Runtime Error?

A **runtime error** occurs while the program is running (after compilation). These errors are not detected by the compiler and often result from logical mistakes, invalid operations, or unexpected conditions (e.g., null values, out-of-bounds access).

#### Examples of Runtime Errors in Dart/Flutter:

1. **Null Reference Error**:
   - Accessing a property or method on a null object.
   ```dart
   void main() {
     String? name;
     print(name.length); // Accessing length on a null value
   }
   ```
   **Error**: `NoSuchMethodError: The getter 'length' was called on null.`

2. **Division by Zero**:
   - Attempting to divide a number by zero.
   ```dart
   void main() {
     int a = 10;
     int b = 0;
     print(a ~/ b); // Integer division by zero
   }
   ```
   **Error**: `IntegerDivisionByZeroException`

3. **Out-of-Bounds Access**:
   - Accessing an index that doesn't exist in a list.
   ```dart
   void main() {
     List<int> numbers = [1, 2, 3];
     print(numbers[5]); // Index out of range
   }
   ```
   **Error**: `RangeError (index): Index out of range`

4. **Invalid Cast**:
   - Trying to cast an object to an incompatible type.
   ```dart
   void main() {
     Object text = "Hello";
     int number = text as int; // Invalid cast
   }
   ```
   **Error**: `type 'String' is not a subtype of type 'int' in type cast`

5. **Flutter-Specific Runtime Errors**:
   - Using a `Future` without awaiting it.
   ```dart
   Future<String> fetchData() async {
     await Future.delayed(Duration(seconds: 2));
     return "Data";
   }

   void main() {
     String data = fetchData(); // Forgot to await the Future
     print(data);
   }
   ```
   **Error**: `type 'Future<String>' is not a subtype of type 'String'`

---

### Key Differences Between Compile-Time and Runtime Errors

| **Aspect**            | **Compile-Time Error**                          | **Runtime Error**                          |
|------------------------|------------------------------------------------|--------------------------------------------|
| **When it occurs**     | During compilation (before the program runs).  | During execution (after the program runs). |
| **Detection**          | Detected by the compiler.                      | Not detected by the compiler.              |
| **Causes**             | Syntax errors, type mismatches, etc.           | Logical errors, null values, etc.          |
| **Examples**           | Missing semicolon, incorrect type usage.       | Null reference, division by zero.          |
| **Fix**                | Fix the code before running.                   | Debug and handle exceptions.               |

---

### How to Handle Runtime Errors in Dart/Flutter

1. **Null Safety**:
   - Use Dart's null safety feature to avoid null reference errors.
   ```dart
   void main() {
     String? name;
     print(name?.length ?? "Name is null"); // Safe access
   }
   ```

2. **Try-Catch Blocks**:
   - Use `try-catch` to handle exceptions gracefully.
   ```dart
   void main() {
     try {
       int a = 10;
       int b = 0;
       print(a ~/ b);
     } catch (e) {
       print("Error: $e");
     }
   }
   ```

3. **Assertions**:
   - Use `assert` to catch logical errors during development.
   ```dart
   void main() {
     int age = -5;
     assert(age >= 0, "Age cannot be negative");
   }
   ```

4. **Flutter Error Handling**:
   - Use `ErrorWidget` or `FlutterError.onError` to handle errors in Flutter apps.
   ```dart
   void main() {
     FlutterError.onError = (details) {
       print("Flutter error: ${details.exception}");
     };
     runApp(MyApp());
   }
   ```

---

By understanding and handling compile-time and runtime errors effectively, you can build more robust and reliable Dart/Flutter applications.

### Difference Between **Authentication** and **Authorization**

| **Aspect**              | **Authentication**                                                                 | **Authorization**                                                                 |
|--------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Definition**           | Verifies **who you are**.                                                         | Determines **what you can do**.                                                  |
| **Purpose**              | Confirms the identity of a user or system.                                         | Grants or restricts access to resources based on permissions.                    |
| **When it Occurs**       | Happens first, during login or access attempts.                                    | Happens after successful authentication.                                         |
| **Example**              | Logging in with a username and password.                                          | Checking if a user has permission to view a specific page or perform an action.  |
| **Methods**              | - Passwords<br>- Biometrics (fingerprint, face recognition)<br>- OTPs             | - Role-Based Access Control (RBAC)<br>- Permissions<br>- Access Control Lists (ACL) |
| **Focus**                | Identity verification.                                                            | Access control.                                                                  |
| **Outcome**              | Grants access to the system.                                                      | Grants access to specific resources or actions.                                  |


### Summary

- **Authentication**: Verifies identity (e.g., login).
- **Authorization**: Grants or restricts access (e.g., role-based permissions).
- Both are essential for building secure and functional applications, especially in Flutter apps that interact with backend services.
