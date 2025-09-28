# Infosys_Springboard
Assignments and Projects for Infosys Springboard
This folder contains the notebook and results for parsing code snippets using AST, tokenization, and embeddings with MiniLM, DistilRoBERTa, and MPNet.
 Background
In modern NLP and code intelligence, embeddings play a crucial role in representing text or source code as dense vectors.  
This project applies the idea to **Python code snippets**, where we:
1. Parse the code using **Abstract Syntax Trees (AST)** to extract structural information (functions, classes, imports, patterns).
2. Tokenize the raw code into lexical elements.
3. Convert the processed representation into **vector embeddings** using pretrained transformer models.
4. Compare how different models (MiniLM, DistilRoBERTa, MPNet) represent the same code.

This helps us understand:
- Which models capture structural similarity better.
- How embeddings cluster for different types of code snippets.
- Methodology

### Step 1: Code Snippets
We selected **10 Python snippets** that include:
- Functions
- Classes
- Imports
- Loops
- Recursion
- Decorators
- Generators
- Data structures (lists, dicts, trees)

### Step 2: AST Parsing
- Used Python’s built-in `ast` module.  
- Extracted:
  - **Functions** (`def ...`)
  - **Classes** (`class ...`)
  - **Imports** (`import ...`, `from ... import ...`)
  - **Patterns**: loops, recursion, decorators, generators  

Example (for a Fibonacci function):
```python
def fib(n):
    a, b = 0, 1
    res = []
    for _ in range(n):
        res.append(a)
        a, b = b, a + b
    return res
