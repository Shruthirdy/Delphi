# Delphi Extension Project

## Introduction
This project involves extending a Pascal grammar to support object-oriented programming features, effectively creating a subset of Delphi. The implemented features include:
- Classes and Objects
- Constructors and Destructors
- Encapsulation

Additionally, a Java interpreter is implemented to process the Abstract Syntax Tree (AST) generated by the ANTLR 4 parser and execute programs written in the extended language.

## Features Implemented
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
│   ├── test2_constructor.pas
│   ├── test3_encapsulation.pas
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
java -cp ".:/Users/shruthiyaramada/Downloads/plp_project1/antlr-4.9.2-complete.jar" Main /Users/shruthiyaramada/Downloads/plp_project1/test/test1_simple_class.pas
```

Repeat the above command with different test files as needed.

## Notes
- Ensure `antlr-4.9.2-complete.jar` is in the correct location.
- The provided test cases cover various functionalities, including classes, constructors, destructors, encapsulation, inheritance, and interfaces.
- Modify `Main.java` if additional debugging or output is required.

## Contact
For any issues or clarifications, feel free to reach out.

---
This concludes the README for the Delphi Extension Project.

