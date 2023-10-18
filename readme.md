## Goal

Write a compiler that is able to process a sub-set of Rust-like features into WASM.

1. Primitive data types (e.g., integers, floating-point numbers, booleans)
2. Variables and assignment
3. Basic arithmetic and logical operations
4. Control structures (e.g., if, while, for)
5. Functions with parameters and return values
6. Simple input/output operations

```rust
// Declare a function to calculate the factorial of a number
function factorial(n: int): int {
    if (n <= 1) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

// Declare a function to calculate the sum of two numbers
function add(a: float, b: float): float {
    return a + b;
}

// Declare a function to print a message based on a boolean value
function printMessage(isTrue: bool) {
    if (isTrue) {
        print("The condition is true.");
    } else {
        print("The condition is false.");
    }
}

// Main program
function main() {
    // Variables and assignment
    int num1 = 5;
    float num2 = 3.5;
    bool flag = true;

    // Basic arithmetic and logical operations
    int sum = num1 + num2;
    int difference = num1 - num2;
    float product = num1 * num2;
    float quotient = num1 / num2;
    bool isGreater = num1 > num2;

    // Control structures (if, while, for)
    if (isGreater) {
        print("num1 is greater than num2.");
    } else {
        print("num1 is not greater than num2.");
    }

    int counter = 0;
    while (counter < 3) {
        print("Counter value: ", counter);
        counter = counter + 1;
    }

    for (int i = 0; i < 5; i = i + 1) {
        print("For loop iteration: ", i);
    }

    // Functions with parameters and return values
    int fact = factorial(num1);
    float additionResult = add(num1, num2);
    print("Factorial of num1: ", fact);
    print("Addition result: ", additionResult);

    // Simple input/output operations
    printMessage(flag);
}

// Call the main function
main();
```


## Week 1: General Architecture Understanding, Language Definition, and Lexical Analysis (Tokenizing)

1. Learn about the basics of compiler architecture, including the main components and their roles (lexical analysis, parsing, semantic analysis, intermediate representation, code generation, and optimization).

2. Define the syntax and semantics of your level 6 language. Write a formal grammar, and decide on the language's data types, control structures, and function handling. You can start with a simple subset of the language and expand it later if desired.

3. Learn about lexical analysis techniques and tools, such as regular expressions and scanner generators like Lex, Flex, or their Rust counterparts.

4. Implement a lexical analyzer (tokenizer) for your language. Write code or rules to recognize keywords, identifiers, literals, operators, and punctuation symbols specific to your language. Ensure that your tokenizer can process a source file and generate a sequence of tokens as output.

## Week 2: Parsing (Syntax Analysis) and Basic Semantic Analysis

1. Learn about parsing techniques, such as recursive descent parsing and parser generators (e.g., LALR or LL). Decide which approach you want to use for your project.

2. Implement a parser that takes the tokens generated by your lexical analyzer and builds an Abstract Syntax Tree (AST) representing the input program's structure. This will involve writing code to handle each of the language constructs (e.g., expressions, control structures, and function declarations).

3. Perform basic semantic analysis during the parsing process. This can include checking for undefined variables and type mismatches, ensuring that variables are declared before use, and enforcing basic scoping rules.

## Week 3: Code Generation, Simple Interpreter, and Testing

1. Learn about different code generation strategies, such as generating bytecode for a virtual machine, generating native code for a specific platform, or generating code in another high-level language.

2. Implement a simple interpreter or code generator for your language. This could involve walking the AST and directly executing the corresponding actions (in the case of an interpreter) or translating the AST into another language (in the case of a code generator).

3. Write test cases to validate the correctness of your compiler or interpreter. Create a set of example programs that cover various language features and edge cases. Test your implementation against these examples to identify and fix any bugs or issues.

4. (Optional) If time permits, start exploring simple optimizations, such as constant folding or dead code elimination, which can be applied during the code generation or interpretation process.
