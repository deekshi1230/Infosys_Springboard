# Infosys_Springboard
Assignments and Projects for Infosys Springboard
This folder contains the notebook and results for parsing code snippets using AST, tokenization, and embeddings with MiniLM, DistilRoBERTa, and MPNet.
## Background
In modern NLP and code intelligence, embeddings play a crucial role in representing text or source code as dense vectors.  
This project applies the idea to **Python code snippets**, where we:
1. Parse the code using **Abstract Syntax Trees (AST)** to extract structural information (functions, classes, imports, patterns).
2. Tokenize the raw code into lexical elements.
3. Convert the processed representation into **vector embeddings** using pretrained transformer models.
4. Compare how different models (MiniLM, DistilRoBERTa, MPNet) represent the same code.

This helps us understand:
- Which models capture structural similarity better.
- How embeddings cluster for different types of code snippets.
## Methodology

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

## Step 3: Tokenization
The source code was tokenized into lexical elements (keywords, identifiers, operators, literals).
Used Python’s tokenize library for precise extraction of tokens.

## Step 4: Embedding Generation
Processed code representations were passed into transformer models:
sentence-transformers/all-MiniLM-L6-v2
distilroberta-base
all-mpnet-base-v2
Each model generated vector embeddings for analysis and comparison.

## Step 5: Similarity Analysis
Cosine similarity and clustering were applied to analyze how snippets with similar logic were grouped.
Comparative results helped identify which model better captured semantic similarity across code samples.

## Key Learnings
AST provides strong structural insight, enhancing embedding interpretation.
MPNet showed higher semantic consistency between functionally similar snippets.
MiniLM was efficient and performed well for short snippets.
The project deepened understanding of code embeddings, representation learning, and semantic search for source code.
