# Delphi Extension Project

## Team Members
- **Yaswanth Attaluri** - UFID: 10136560  
- **Shruthi Yaramada** - UFID: 26497222  

## Introduction
This project involves extending a Pascal grammar to support object-oriented programming features, effectively creating a subset of Delphi. The implemented features include:
- **Classes and Objects**: Support for defining and instantiating classes.
- **Constructors and Destructors**: Automatic initialization and cleanup of objects.
- **Encapsulation**: Use of access modifiers to restrict variable access.
- **Input/Output Functionality**: Integer input and output via the terminal.

### Bonus Features (20% Extra Credit)
- **Inheritance**: Allowing classes to extend other classes.
- **Interfaces**: Defining and implementing interfaces.

## Project Structure
```
plp_project1/
│── src/
│   ├── delphi/
│   │   ├── delphi.g4  # ANTLR grammar for extended Pascal (Delphi)
│   │   ├── *.java     # Generated ANTLR parser and lexer files
│   ├── Main.java      # Java interpreter to walk through the AST
│── test/
│   ├── test1_simple_class.pas
│   ├── test2_const_dest.pas
│   ├── test3_test_inherit.pas
│   ├── test4_test_interface.pas
│   ├── ...            # More test cases
│── README.md          # This file
```

## Setup and Execution

### 1. Download ANTLR 4 Files
Run the following command to get the ANTLR runtime:
```
curl -o antlr-4.9.2-complete.jar https://www.antlr.org/download/antlr-4.9.2-complete.jar
```

### 2. Generate the ANTLR Parser and Lexer
Navigate to the grammar directory:
```
cd plp_project1/src/delphi
```
Generate the necessary Java files:
```
antlr4 -Dlanguage=Java -visitor delphi.g4
```

### 3. Compile the Java Interpreter
Navigate to the project root directory:
```
cd plp_project1
```
Compile the Java files:
```
javac -cp "antlr-4.9.2-complete.jar" -d src/ src/delphi/*.java
```

### 4. Run Test Cases
Navigate to the `src` directory:
```
cd plp_project1/src
```
Run the interpreter with a test case:
```
java -cp ".:/path/to/project/plp_project1/antlr-4.9.2-complete.jar" Main /path/to/project/plp_project1/test/test1_simple_class.pas
```

Repeat the above command with different test files as needed.

## Test Case Explanations

### Test 1: Simple Class Implementation (`test1_simple_class.pas`)
- Demonstrates the ability to define a simple class with attributes and a method.
- Validates object instantiation and method invocation.
- Example: A `Person` class with `name` and `age` fields, and a method to print details.

### Test 2: Constructors and Destructors (`test2_const_dest.pas`)
- Ensures that the constructor initializes object attributes correctly.
- Tests automatic execution of destructors upon object deletion.
- Example: A `Car` class initializes `brand` and `model` in the constructor and releases memory in the destructor.

### Test 3: Inheritance (`test3_test_inherit.pas`)
- Checks that child classes can inherit fields and methods from parent classes.
- Example: `Employee` extends `Person` and adds `salary` attribute.

### Test 4: Interfaces (`test4_test_interface.pas`)
- Ensures interface declaration and implementation by a class.
- Example: A `Drawable` interface with a `draw` method implemented by `Circle` and `Square` classes.

## Notes
- Ensure `antlr-4.9.2-complete.jar` is in the correct location.
- The provided test cases cover various functionalities, including classes, constructors, destructors, encapsulation, inheritance, and interfaces.
- Modify `Main.java` if additional debugging or output is required.
