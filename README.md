# Neural Chef Assistant
**Recipe Generation with RNN-based Seq2Seq Models**

This project explores the use of RNN-based sequence-to-sequence models to generate step-by-step cooking recipes from a list of ingredients. Implemented as part of Monash University's FIT5217 Deep Learning course.



##  Overview

Given a list of ingredients like:

["sugar", "lemon juice", "strawberries", "icecream"]


The model generates a recipe such as:

Mix strawberries with sugar and lemon juice. Freeze the mixture. Serve with icecream on top.


This is a **text generation** task using **RNN encoder-decoder architectures**, enhanced with attention, copy, and coverage mechanisms.



##  Project Files

| Notebook | Description |
|----------|-------------|
| `base1.ipynb` | Baseline 1: Seq2Seq without attention |
| `base2.ipynb` | Baseline 2: Seq2Seq with attention |
| `mild1.ipynb` | Mild Extension 1: Domain-specific preprocessing |
| `mild2.ipynb` | Mild Extension 2: Hidden size ↑, dropout, tuning |
| `spicy1.ipynb` | Spicy Extension 1: Pointer-Generator Network |
| `spicy2.ipynb` | Spicy Extension 2: Coverage Mechanism |



## Model Techniques

- **GRU-based encoder-decoder**
- **Bahdanau attention**
- **Preprocessing**: stopword removal, unit filtering, vocabulary pruning
- **Copy mechanism**: dynamic switch between generation and copying
- **Coverage mechanism**: avoid repetition, track attended context



##  Evaluation Metrics

All models were evaluated on the test set using:

- **BLEU-4**
- **METEOR**
- **BERTScore (F1)**

Example results:

| Model | BLEU-4 | METEOR | BERTScore |
|-------|--------|--------|-----------|
| Baseline 2 | 0.0604 | 0.3006 | 0.7558 |
| Mild 2     | **0.1072** | **0.4228** | **0.8013** |
| Spicy 1    | 0.0767 | 0.3758 | 0.7836 |



## Qualitative Comparison

Two ingredient lists were used to compare model outputs:

**Sample 1 Ingredients**:  
`sugar`, `lemon juice`, `orange juice`, `water`, `strawberries`, `icecream`

**Sample 2 Ingredients**:  
`philadelphia cream cheese`, `condensed milk`, `vanilla`, `lemon juice`, `canned cherries`, `graham cracker`, `pie crust`

**Findings**:
- Mild Extension 2 generated the most coherent and complete recipes.
- Pointer mechanism helped include ingredient terms more accurately.
- Coverage model was prone to hallucination and repetition.



## Key Learnings

- Preprocessing and architecture tuning improve performance more than complex add-ons.
- Copying ingredients is essential for recipe realism.
- Coverage mechanisms require careful tuning to work as intended.


## Author

YA LIU  
Master of Artificial Intelligence, Monash University  
July 2025

