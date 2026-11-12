# Part C: Specialized Technology (Natural Language Processing)

## C1. Fundamental Concepts

The specialized technology selected for this project is **Natural Language Processing (NLP)** integrated with **Content-Based Filtering** and an **Offline-First Synchronization Architecture**. Traditional culinary databases rely on rigid SQL query execution that requires exact string matches (e.g., matching the exact term "chicken" with "chicken"). When home cooks input arbitrary, sparse, or non-standard leftover ingredient descriptions (e.g., "200g organic fresh chicken breast" or "diced tomatoes"), static database filters fail to match recipe items, resulting in search failures and user frustration (Peng, 2024).

To resolve these limitations, modern meal planning systems apply NLP pre-processing pipelines within a Vector Space Model (VSM) to transform unstructured ingredient text into continuous, high-dimensional numerical weight matrices (Pal, 2023). As illustrated in Figure 1, the system executes a four-stage processing pipeline:

1. **Tokenization and Normalization:** User-inputted ingredient strings are converted to lowercase and split into atomic tokens (e.g., "Fresh Diced Tomatoes" -> `['fresh', 'diced', 'tomatoes']`) (Pal, 2023).
2. **Stop-Word Removal and Aspect Extraction:** Non-essential descriptors, quantities, and measurement units (e.g., "grams", "chopped", "fresh") are stripped to isolate the core ingredient noun (`['tomato']`) (Pal, 2023).
3. **TF-IDF Vectorization:** Cleaned ingredient lists are transformed into numerical weight matrices using Term Frequency-Inverse Document Frequency (TF-IDF) (Pal, 2023).
4. **Cosine Similarity Computation:** The engine computes the mathematical proximity between the user's active pantry vector (A) and candidate recipe vectors (B) using the formula `Cosine(A, B) = (A · B) / (||A|| × ||B||)` to rank recipes by similarity percentage (Pal, 2023; Ruiz-Rincón & Galpin, 2024).

```text
+---------------------------------------------------------------------+
|                       INPUT: Raw Pantry Text                          |
|             (e.g., "Fresh Diced Tomatoes, 250g Chicken")              |
+---------------------------------------------------------------------+
                                   |
                                   v
+---------------------------------------------------------------------+
| Stage 1: Tokenization & Normalization                                 |
| - Convert text to lower-case                                          |
| - Split text into atomic tokens: ['fresh', 'diced', 'tomatoes']       |
+---------------------------------------------------------------------+
                                   |
                                   v
+---------------------------------------------------------------------+
| Stage 2: Stop-Word Removal & Aspect/Descriptor Filtering              |
| - Filter non-essential attributes (units, quantities, adjectives)     |
| - Isolate core ingredient noun: Cleaned = ['tomato', 'chicken']       |
+---------------------------------------------------------------------+
                                   |
                                   v
+---------------------------------------------------------------------+
| Stage 3: TF-IDF Vectorization                                         |
| - Convert cleaned ingredient tokens into numerical weight matrices    |
+---------------------------------------------------------------------+
                                   |
                                   v
+---------------------------------------------------------------------+
| Stage 4: Cosine Similarity Engine                                     |
| - Compute mathematical distance between pantry and recipe vectors     |
| - Output similarity score: Cosine(A, B) = (A . B) / (||A|| * ||B||)   |
+---------------------------------------------------------------------+
                                   |
                                   v
+---------------------------------------------------------------------+
|                      OUTPUT: Ranked Recipe List                       |
|        (e.g., Recipe 1: 81.65% Match, Recipe 2: 0.00% Match)          |
+---------------------------------------------------------------------+
