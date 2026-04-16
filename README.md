# Expression Converter

A Java program that converts **infix expressions** into **postfix** and **prefix** forms using the **Shunting-yard algorithm**.  
This project demonstrates tokenization, operator precedence handling, and expression conversion techniques.

---

## 🚀 Features
- Tokenizes infix expressions into operands, operators, and parentheses.
- Converts infix expressions to **postfix (Reverse Polish Notation)**.
- Converts infix expressions to **prefix (Polish Notation)** using the reverse-and-swap method.
- Handles:
  - Multi-digit numbers
  - Single-letter variables
  - Standard operators: `+ - * / ^`
  - Parentheses for grouping

---

## 📂 Project Structure
- **`tokenize()`** → Breaks input into tokens (numbers, variables, operators, parentheses).
- **`infixToPostfix()`** → Implements the Shunting-yard algorithm.
- **`toPostfix()`** → Converts infix to postfix (string output).
- **`toPrefix()`** → Converts infix to prefix using reverse-and-swap.
- **`main()`** → Accepts user input and prints infix, postfix, and prefix forms.

---

## 📊 Flow Chart (Vertical Summary)

Start
│
▼
User inputs infix expression
│
▼
Tokenize expression → build tokens
│
▼
Convert to Postfix (Shunting-yard)
│
▼
Convert to Prefix (reverse + swap + postfix + reverse)
│
▼
Display results (Infix, Postfix, Prefix)
│
▼
End


---

## 📝 Pseudocode

FUNCTION tokenize(infix):
FOR each character:
IF whitespace → skip
IF digit → build number
IF letter → add variable
IF operator/parenthesis → add
RETURN tokens

FUNCTION infixToPostfix(tokens):
FOR each token:
IF operand → output
IF "(" → push
IF ")" → pop until "("
IF operator → check precedence, pop higher/equal, push current
Pop remaining operators
RETURN postfix list

FUNCTION toPostfix(infix):
tokens = tokenize(infix)
RETURN infixToPostfix(tokens)

FUNCTION toPrefix(infix):
tokens = tokenize(infix)
reverse tokens
swap "(" and ")"
postfixOfRev = infixToPostfix(reversed tokens)
reverse postfixOfRev
RETURN prefix

MAIN:
read infix from user
print infix, postfix, prefix

---

## 🖥️ Example Run

Enter infix expression (e.g., (10 + 2) * 3^2 or A + B * C): (10 + 2) * 3^2

Infix   : (10 + 2) * 3^2
Postfix : 10 2 + 3 2 ^ *
Prefix  : * + 10 2 ^ 3 2

---

## 📌 Use Cases
- Educational tool for learning expression conversion.
- Basis for building compilers or interpreters.
- Practice with data structures (Stacks, Lists).

---

## ⚙️ Requirements
- Java 17+ (or any version supporting `switch` expressions).
- Command-line interface.

---
