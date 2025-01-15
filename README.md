# Flutter Interview Questions
1- What is OOP | Main Principles | Examples ?

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
