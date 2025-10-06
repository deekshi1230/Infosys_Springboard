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
Used Python’s tokenize library to convert code into a sequence of tokens:
keywords, variables, literals, and operators.
This helps the model focus on meaningful language patterns.
Example Tokens:
['def', 'fib', '(', 'n', ')', ':', 'for', 'in', 'range', 'return']

## Step 4: Embedding Generation
Processed code representations were passed into transformer models:
sentence-transformers/all-MiniLM-L6-v2
distilroberta-base
all-mpnet-base-v2
Each model generated vector embeddings for analysis and comparison.
Generated embeddings using pretrained transformer models from Hugging Face:
🟦 sentence-transformers/all-MiniLM-L6-v2
🟩 distilroberta-base
🟪 all-mpnet-base-v2
Each model converts the code snippet into a vector of 384–768 dimensions representing its meaning.

## Step 5: Similarity Analysis
Cosine similarity and clustering were applied to analyze how snippets with similar logic were grouped.
Comparative results helped identify which model better captured semantic similarity across code samples.
Visualized results using:
2D projections via PCA and t-SNE
Heatmaps for similarity comparison
Scatter plots to show clustering behavior

 ## Sample Results
Code Snippet Pair	MiniLM Similarity	DistilRoBERTa	MPNet	Closest Match
| Code Snippet Pair                | MiniLM Similarity | DistilRoBERTa | MPNet    | Closest Match |
| -------------------------------- | ----------------- | ------------- | -------- | ------------- |
| Fibonacci ↔ Factorial            | 0.72              | 0.68          | **0.81** | MPNet         |
| List Sum ↔ Array Sum             | **0.89**          | 0.77          | 0.85     | MiniLM        |
| Class Parser ↔ Decorator Example | 0.56              | 0.61          | **0.68** | MPNet         |


## Key Learnings
AST parsing gives interpretable insight into code’s logic and structure.
Transformer-based embeddings capture semantic relationships effectively.
MPNet offered the best overall balance between precision and interpretability.
Understanding embeddings for code is foundational for AI-powered programming tools.


## Tech Stack
| Category    | Tools & Libraries                                                                                           |
| ----------- | ----------------------------------------------------------------------------------------------------------- |
| Language    | Python 3.x                                                                                                  |
| NLP Models  | `MiniLM`, `DistilRoBERTa`, `MPNet`                                                                          |
| Libraries   | `ast`, `tokenize`, `transformers`, `sentence-transformers`, `numpy`, `pandas`, `scikit-learn`, `matplotlib` |
| Environment | Jupyter / Google Colab                                                                                      |


