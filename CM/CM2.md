# CM2

## Table of Contents
- [CM2](#cm2)
  - [Table of Contents](#table-of-contents)
  - [Quiz 1 Rubric](#quiz-1-rubric)
  - [Computing for Medicine, Lecture 6: Word Vectors and Embeddings for Computing in Medicine](#computing-for-medicine-lecture-6-word-vectors-and-embeddings-for-computing-in-medicine)

## Quiz 1 Rubric

- CMQuiz1.pdf Read it 

## Computing for Medicine, Lecture 6: Word Vectors and Embeddings for Computing in Medicine

**Course:** Computing for Medicine  
**Google Classroom Code:** dnd5qkt5  
**Semester:** Monsoon 2025  
**Lecture:** 6  

---

### International Classification of Diseases (ICD)

The International Classification of Diseases (ICD) is a globally used diagnostic classification system for epidemiology, health management, and clinical purposes.

#### ICD-10 Chapter Classifications

| Code | ICD-10 Chapter | Range |
|------|----------------|--------|
| I | Certain infectious and parasitic diseases | A00-B99 |
| II | Neoplasms | C00-D48 |
| III | Diseases of the blood and blood-forming organs and certain disorders involving the immune system | D50-D89 |
| IV | Endocrine, nutritional and metabolic diseases | E00-E90 |
| V | Mental and behavioral disorders | F00-F99 |
| VI | Diseases of the nervous system | G00-G32 |
| VII | Diseases of the eye and adnexia | H00-H59 |
| VIII | Diseases of the ear and mastoid process | H60-H95 |
| IX | Diseases of the circulatory system | I00-I99 |
| X | Diseases of the respiratory system | J00-J99 |
| XI | Diseases of the digestive system | K00-K93 |
| XII | Diseases of the skin and subcutaneous tissue | L00-L99 |
| XIII | Diseases of the musculoskeletal system and connective tissue | M00-M99 |

#### ICD Coding for Respiratory System (J00-J99)

| Section | Code Range |
|---------|------------|
| Acute upper respiratory infections | J00-J06 |
| Influenza and pneumonia | J10-J18 |
| Other acute lower respiratory infections | J20-J22 |
| Other diseases of the upper respiratory tract | J30-J39 |
| Chronic lower respiratory diseases | J40-J47 |
| Lung diseases due to external agents | J60-J70 |
| Other respiratory diseases principally affecting the interstitium | J80-J84 |
| Suppurative and necrotic conditions of the lower respiratory tract | J85-J86 |
| Other diseases of the pleura | J90-J94 |
| Other diseases of the respiratory system | J95-J99 |

---

### Basic Idea Behind All Modern Representations

Modern representation learning follows a pipeline:

```
Input Space → Feature Space → Abstract Representation Learning (Deep Learning) → Output Space
```

This process transforms raw data into meaningful representations that can be processed by machine learning algorithms.

---

### Word Embeddings

#### Definition
Word embeddings are mathematical representations of language units that capture semantic meaning and relationships between words.

#### Types of Word Representations

1. **Basic vectorization approaches**
2. **Distributed representations**
3. **Universal language representation**
4. **Handcrafted features**

#### Motivation
The goal is to capture the meaning of language rather than just structure.

#### Process Steps
1. Break the sentence into lexical units such as lexemes, words, and phrases
2. Derive the meaning for each of the lexical units
3. Understand the syntactic (grammatical) structure of the sentence
4. Understand the context in which the sentence appears

---

### Featurization Methods

#### One Hot Encoding

One Hot Encoding maps each word to a unique position in a vector where only one element is 1 and all others are 0.

##### Process
- Map each word w → a unique integer wid between 1 and |V|
- Each word becomes a V-dimensional binary vector
- Example: Dog = [1 0 0 0 0 0]
- "Dog Bites Man" = [ [1 0 0 0 0 0] [0 1 0 0 0 0] [0 0 1 0 0 0]]

##### Implementation Example

```python
sentences = ["It was the best of times",
"it was the worst of times",
"it was the age of wisdom",
"it was the age of foolishness"]

tokenized_sentences = [[t for t in sentence.split()] for sentence in sentences]
vocabulary = set([w for s in tokenized_sentences for w in s])

import pandas as pd
pd.DataFrame([[w, i] for i,w in enumerate(vocabulary)])
```

```python
def onehot_encode(tokenized_sentence):
    return [1 if w in tokenized_sentence else 0 for w in vocabulary]

onehot = [onehot_encode(tokenized_sentence)
          for tokenized_sentence in tokenized_sentences]

for (sentence, oh) in zip(sentences, onehot):
    print("%s: %s" % (oh, sentence))
```

##### Output Example
```
[0, 1, 1, 0, 0, 1, 1, 0, 0, 1, 1]: It was the best of times
[1, 1, 1, 0, 0, 0, 1, 1, 0, 1, 0]: it was the worst of times
[0, 1, 1, 0, 1, 0, 0, 1, 1, 1, 0]: it was the age of wisdom
[0, 1, 1, 1, 1, 0, 0, 1, 0, 1, 0]: it was the age of foolishness
```

##### Challenges of One Hot Encoding
- Size of a one-hot vector ∝ size of the vocabulary |V|
- Sparse representations - matrix full of zeroes
- Storage constraints and overfitting due to sparsity
- Does not give fixed length representation
- Assumes independence between words
- Out of Vocabulary (OOV) problem - needs retraining every time a new word is added

#### Bag of Words (BoW)

##### Concept
- Assumes that text belonging to a given class in the dataset is characterized by a unique set of words
- Knowing the words present in a text tells about the class (bag)
- Each document is a V-dimensional vector
- Example: "Dog Bites Man" = [1 1 1 0 0 0]

##### Advantages
- Gives a fixed length representation
- Captures some semantic similarity of documents

##### Challenges with BoW Representation
- Sparsity
- Same word may mean different things in different contexts
- Out of Vocabulary (OOV) words
- Order information is lost

#### Bag of N-Grams (BoN)

##### Purpose
Attempts to preserve context and order information by considering sequences of words.

##### Example
- Bigrams = {dog bites, bites man, man bites, bites dog, dog eats, eats meat, man eats, eats food}
- "Dog Bites Man" = [1,1,0,0,0,0,0,0]

##### Types
- Bigram (2 words)
- Trigram (3 words)
- N-gram (n words)

---

### Discriminative vs Generative AI

#### Discriminative Models
- Learn p(y|x) - probability of output given input
- Focus on decision boundaries

#### Generative Models
- Learn p(x,y) - joint probability distribution
- Can generate new data samples

#### Text Generation Models (Large Language Models)
Modern language models can take text input and generate coherent text output, such as summarizing articles.

---

### Probabilistic Autoregressive Models (Traditional Models)

#### Concept
Traditional language models assign probabilities to word sequences.

##### Example
For the sentence "John bought a book":
- p(John, bought, a, book) = 0.02
- p(book, bought, a, John) = 0.01
- p(book, a, John, bought) = 0.0001

##### Sequential Generation
```
John bought a
John bought a book
John bought a book for
John bought a book for coloring
```

##### Mathematical Formulation
p(John, bought, a, book) = p(John) × p(bought | John) × p(a | John, bought) × p(book | John, bought, a)

---

### Vector Space Paradigm: Distributional Hypothesis

#### Core Quote
**"You shall know a word by the company it keeps!"** - Firth (1957)

#### Distributional Representation
Inducing distributional properties from context to generate a representation. Words that appear in similar contexts tend to have similar meanings.

---

### Core Idea: Vector Space

#### Key Principles
- Represent words (or tokens) as vectors
- Words with similar meanings have related vector representations
- Associations between words are captured in shared weights
- Vector weights can be trained using neural networks

#### Word Algebra
Vector representations allow mathematical operations on words:

```
KING - MAN + WOMAN = QUEEN
UNCLE - MAN + WOMAN = AUNT
```

This demonstrates that word vectors capture semantic relationships and analogies.

---

### How Embeddings Capture Context

Word embeddings can distinguish between different meanings of the same word based on context. For example, the word "lie" has multiple meanings:

#### Different Contexts of "Lie"

##### Untruth (verb)
- "I will lie for personal benefit"
- "Rob reveals to Tracy that everything was a lie and that he still hated her"

##### Mathematical Sense (verb)
- "A skew polygon does not lie in a flat plane, but zigzags in three (or more) dimensions"
- "As an open string propagates through spacetime, its endpoints are required to lie on a D-brane"

##### Lie Down (verb)
- "There Fenrir will lie until Ragnarok"
- "They lie down to sleep deeply"

##### Geographical (island) - (verb)
- "Some 3,579 islands lie adjacent to the peninsula"
- "The islands lie on the Kerguelen Plateau in the Indian Ocean"

##### Conceptual Placement (verb)
- "According to Dewey, conversation, debate and dialogue lie at the heart of a democracy"
- "The origins of mathematical thought lie in the concepts of number, magnitude and form"

##### Geographical (other) - (verb)
- "Very small portions lie within the Pueblo County School District 70"
- "The ruins of the town lie along the river Ziz in the Tafilalt oasis near the town of Rissani"

---

### Word2Vec (Generation 1)

Word2Vec is a popular method for creating word embeddings using neural networks.

#### Continuous Bag of Words (CBOW)

##### Concept
- Predicts the middle word given the context
- Assigns probability to sentences such that "good" sentences are maximized

##### Example
```
The quick brown fox jumped over the lazy dog
```

##### Training with CBOW

**Source Text:** "The quick brown fox jumps over the lazy dog."

**Training Samples (context, target):**
- ((quick, brown), The)
- ((The, brown, fox), quick)
- ((The, quick, fox, jumps), brown)
- ((quick, brown, jumps, over), fox)

#### Skip-Gram Variant

##### Concept
Predicts the context given the middle word.

##### Example
```
The quick brown fox jumped over the lazy dog
```

##### Training with Skip-Gram

**Source Text:** "The quick brown fox jumps over the lazy dog."

**Training Samples (target, context):**
- (the, quick)
- (the, brown)
- (quick, the)
- (quick, brown)
- (quick, fox)
- (brown, the)
- (brown, quick)
- (brown, fox)
- (brown, jumps)
- (fox, quick)
- (fox, brown)
- (fox, jumps)
- (fox, over)

---

### Summary

Word vectors represent a fundamental shift from traditional symbolic representations to distributed representations that capture semantic meaning. The evolution from one-hot encoding to sophisticated embedding methods like Word2Vec demonstrates the progression toward more meaningful and efficient representations of language for computational processing.

Key takeaways:
1. Traditional methods like one-hot encoding and bag-of-words have limitations in capturing semantic relationships
2. Distributional hypothesis forms the foundation for modern word embeddings
3. Word2Vec methods (CBOW and Skip-Gram) learn dense vector representations that capture semantic and syntactic relationships
4. Context plays a crucial role in determining word meaning and embeddings capture this through distributional patterns

## Computing for Medicine, Lecture 7: Embeddings + Transformers

Google Classroom Code: `dnd5qkt5`
Monsoon 2025

---

### Word Vectors

#### Training with CBOW (Continuous Bag of Words)

**Source Text:**
```
The quick brown fox jumps over the lazy dog.
```
Repeated for multiple training samples.

**Training Samples (context, target):**
- (quick, brown) → The
- (The, brown, fox) → quick
- (The, quick, fox, jumps) → brown
- (quick, brown, jumps, over) → fox

##### CBOW Model Architecture
- **Input Layer:** words from context
- **Hidden Layer:** sums up context vectors
- **Output Layer:** predicts the target word
- Dimensionality:
  - N-dim (hidden)
  - V-dim (output)

---

#### word2Vec: Skip Gram Variant

- **Skip Gram** predicts the context given the middle word.
- Example text:
```
The quick brown fox jumped over the lazy dog.
```

**Training Samples (target, context):**
- (the, quick)
- (the, brown)
- (quick, the)
- (quick, brown)
- (quick, fox)
- (brown, the)
- (brown, quick)
- (brown, fox)
- (brown, jumps)
- (fox, quick)
- (fox, brown)
- (fox, jumps)
- (fox, over)

##### Continuous SkipGram Model Architecture
- **Input Layer:** target word
- **Hidden Layer:** context features
- **Output Layer:** context prediction
- Dimensionality:
  - N-dim (hidden)
  - V-dim (output)

---

### Key Papers in Word Embeddings

#### Efficient Estimation of Word Representations in Vector Space
- **Authors:** Tomas Mikolov, Greg Corrado, Kai Chen, Jeffrey Dean
- **Published by:** Google Inc., Mountain View, CA

#### Distributed Representations of Words and Phrases and their Compositionality
- **Authors:** Kai Chen, Jeffrey Dean, Tomas Mikolov, Ilya Sutskever, Greg Corrado
- **Published by:** Google Inc.

---

### Open Source Code: Multiple Implementations
- **word2vec project:**
  - Efficient implementation for continuous bag-of-words and skip-gram architectures
  - Used for vector representations of words
- **Quick Start:**
  - Download code via SVN:
    ```
    svn checkout http://word2vec.googlecode.com/svn/trunk
    ```
- **License:** Apache License 2.0

---

### Words in Vector Space (Example Embedding)

| Word      | Embedding (example) |
|-----------|---------------------|
| pandemic  | [0.3, 0.8]          |
| covid     | [0.3, 0.7]          |
| hospital  | [0.4, 0.5]          |
| football  | [0.9, 0.1]          |


### Summary of Embeddings
- **Embeddings capture distributional similarities between words**
- Enable efficient word algebra and analogies
- **Popular Models**:
  - Word2Vec: Pre-trained neural network-based embedding (Unit = Word)
  - GloVe: Pretrained word embedding from Stanford (Unit = Word)
  - FastText: Pretrained embedding from Facebook (Unit = Character)

---

### Pretrained Embeddings for Clinical Data and Concepts

#### Available Models

| Name                           | Model      | Data/Concepts                           | Terms       | Dimension | 
|--------------------------------|------------|-----------------------------------------|-------------|-----------| 
| PubMed-w2v.bin                 | word2vec   | PubMed                                  | 2.4M        | 200       |
| PMC-w2v.bin                    | word2vec   | PubMed Central                          | 25M         | 200       |
| PubMed-and-PMC-w2v.bin         | word2vec   | PubMed, PubMed Central                  | 4.1M        | 200       |
| wikipedia-pubmed-and-PMC-w2v   | word2vec   | PubMed, PubMed Central, Wikipedia       | 5.5M        | 200       |
| drug word embeddings           | word2vec   | PubMed, DrugBank                        | 553,195     | 420       |
| AWE-CM [49]                    | word2vec   | UMLS CUI (concepts)                     | 265M        | 300       |
| claims_codes_hs_300 [55]       | word2vec   | ICD-9 codes (concepts)                  | 51,327      | 300       |
| claims_cuis_hs 300 [55]        | word2vec   | UMLS CUI (concepts)                     | 14,852      | 300       |
| cui2vec [56]                   | word2vec/Glove | UMLS CUI (concepts)                  | 108,477     | 500       |
| concept embeddings [58]        | AiTextML   | MeSH ID (concepts)                      | 26,103      | 100       |
| word embeddings [58]           | AlTextML   | PubMed                                  | 513,196     | 100       |
| ELMO (PubMed model) [11]       | ELMO       | PubMed                                  | N/A         | 1024      |
| BioBERT [15]                   | BERT       | PubMed                                  | N/A         | 768/1024  |
| ClinicalBERT [16,17]           | BERT       | MIMIC III                               | N/A         | 768       |

**Key Points:**
- **ELMO** models use character information
- **BERT** models use sub-word information
- Can represent any concept

---

### Evaluation Tasks for Word Embeddings

- **Evaluation metrics:** relatedness, similarity, cluster quality, conceptual similarity, clinical information extraction, disease prediction, mortality prediction, NER, drug name recognition, high-risk prediction, phenotype classification, term abstraction, etc.
- **Studies:** De Vise et al., Chie et al., Dubois et al., Wang et al., etc.
- **Corpora examples:**
  - PubMed, PMC
  - Mayo Clinic notes, OHSUMED
  - Google News
  - MedHelp forum
  - Medical claims
  - UMLS, MeSH
  - MIMIC-III
  - Wikipedia

---

### Sequence Models and Transformers

#### Sequence to Sequence Modeling — Encoder-Decoder Framework

##### Example
- **INPUT:** Je suis étudiant
- **OUTPUT:** I am a student

###### Structure
- **Encoder:** Processes input sequence
- **Decoder:** Produces output sequence

###### Steps
1. Embedding words from input
2. Apply encoder at each time step
3. Use decoder to predict output words step by step

---

#### Attention and Transformer Architecture

##### "Attention Is All You Need" (Vaswani et al., 2017)
- **Main authors:** Ashish Vaswani, Noam Shazeer, Niki Parmar, Llion Jones, Aidan Gomez, Jakob Uszkoreit, Łukasz Kaiser, Illia Polosukhin

###### Transformer Structure (Block Diagram)
```
Nx layers:
- Add & Norm
- Multi-Head Attention
- Feed Forward
- Softmax Output
Input: Embedded sequence + Positional Encoding
Output: Embedded sequence + Positional Encoding
Masked Multi-Head Attention in decoder
```

###### Input Embeddings (Sample Words)
- microwave, refrigerator, bulb, kitchen, light, charger, battery, sink, bathroom, etc.

###### Positional Encoding
- Adds position information to input embeddings.

---

#### Attention Mechanism

##### Principle
- Context Vector Calculation:
  - For each output token, compute weighted sum over encoder hidden states.
  - Formula:
    ```
    C_i = Σ a_ij h_j
    a_ij = exp(e_ij) / Σ_k exp(e_ik)
    e_ij = alignment score for i-th decoder state vs j-th encoder state
    ```

---

#### Self Attention
- Each word attends to other words in the sequence to capture context.
- Calculation cost: O(n²) (quadratic in sequence length)

###### Query, Key, and Value Representation
- For each input, derive three vectors:
    - Query (q)
    - Key (k)
    - Value (v)
- Compute attention scores as dot products of queries and keys:
    ```
    Attention(Q, K, V) = softmax( Q × K^T / sqrt(d_k) ) × V
    ```

###### Masked Attention
- Prevents decoder from attending to future positions
- Look-ahead masking used in generation tasks (next word prediction)

---

#### Resources
- Code and downloads:
  - http://evexdb.org/pmresources/ngrams/PubMed/ 
  - http://evexdb.org/pmresources/ngrams/PMC/ 
  - http://evexdb.org/pmresources/vec-space-models/wikipedia-pubmed-and-PMC-w2v.bin
  - https://github.com/chop-dbhi/drug_word_embeddings
  - Visual Guides:
      - https://jalammar.github.io/illustrated-transformer/
      - https://becominghuman.ai/attention-is-all-you-need-16bf481d8b5c
      - http://peterbloem.nl/blog/transformers

---

#### End of Lecture

Thanks for attending the class!

## Computing for Medicine, Lecture 8: Transformer (Continued)

**Course:** Computing for Medicine  
**Google Classroom Code:** dnd5qkt5  
**Semester:** Monsoon 2025  
**Lecture:** 8 - Transformer (Continued)

---

### Recap: Transformer Architecture

#### Complete Transformer Structure

The Transformer consists of two main components:

1. **Encoder Stack** (left side)
   - N identical layers (Nx)
   - Each layer contains:
     - Multi-Head Attention
     - Add & Norm
     - Feed Forward
     - Add & Norm

2. **Decoder Stack** (right side)
   - N identical layers (Nx)
   - Each layer contains:
     - Masked Multi-Head Attention
     - Add & Norm
     - Multi-Head Attention (encoder-decoder attention)
     - Add & Norm
     - Feed Forward
     - Add & Norm

#### Key Components Flow

```
Input → Input Embedding → Positional Encoding → Encoder Stack
Output (shifted right) → Output Embedding → Positional Encoding → Decoder Stack
Decoder Stack → Linear → Softmax → Output Probabilities
```

---

### Scaled Dot Product Attention (Similarity with Context)

#### Mathematical Formula

```
Attention(Q, K, V) = softmax(QK^T / √dk) V
```

#### Components Explained

- **Q (Query):** "What am I asking about?" - the search intent
- **K (Key):** "Where should I look?" - addressing mechanism  
- **V (Value):** "What information do I retrieve once I've found the right spots?" - actual content

#### Processing Steps

1. **Matrix Multiplication:** QK^T
2. **Scaling:** Divide by √dk (where dk is dimension of keys)
3. **Softmax:** Convert to probability distribution
4. **Value Retrieval:** Multiply with V matrix

#### Visual Example

Example sentence: "like this movie very much !"

The attention mechanism processes this through:
- MatMul operation
- Scale by √dk (where d=5 in example)
- Apply SoftMax
- Optional Mask
- Final MatMul with Values

---

### Mechanics of Attention - Step by Step

#### Step 1: Generate Similarity Score

Like "n judges scoring m keys" - creates similarity matrix between queries and keys.

#### Step 2: Scale and Softmax

- **Scaling:** Prevents extremely large values that could cause vanishing gradients
- **Softmax:** Turns each row into a probability distribution
- Each row sums to 1.0

#### Step 3: Retrieve the Values (Output Embeddings)

Use the probability weights to get weighted sum of value vectors.

---

### Analogies for Understanding Query, Key, Value

#### Library Analogy

**Scenario:** You're searching for books in a library

- **Key (K):** Book's index card used to locate it
- **Query (Q):** Your search question  
- **Value (V):** The actual book content you take home once you've matched the index card

#### Practical Example

When processing "he bought books":
- "he": 30% attention weight
- "bought": 50% attention weight  
- "books": 0.1% attention weight
- "a": 0.1% attention weight
- "boy": 0.1% attention weight

---

### Masked Attention

#### Purpose

Prevents the decoder from "looking ahead" at future tokens during training.

#### Look-Ahead Mask

```
Raw attention weights → Apply mask → Masked attention
```

#### Matrix Representation

The mask matrix has:
- 1s for allowed connections
- 0s for blocked connections (future positions)

Example mask pattern:
```
1 0 0 0 0
1 1 0 0 0  
1 1 1 0 0
1 1 1 1 0
1 1 1 1 1
```

#### Sequence Processing

- y1 can only attend to x1
- y2 can attend to x1, x2
- y3 can attend to x1, x2, x3
- And so on...

This ensures that position i can only attend to positions less than i.

---

### Multi-Head Attention

#### Architecture

```
Input → Linear Transformations (Q, K, V) → h parallel attention heads → Concat → Linear → Output
```

#### Mathematical Process

1. **Linear Transformations:** Apply separate linear layers to create Q, K, V for each head
2. **Parallel Processing:** Run h attention heads in parallel
3. **Concatenation:** Combine outputs from all heads
4. **Final Linear:** Apply final linear transformation

#### Key Insight

**Mathematical principle:** One big linear function, then splitting allows each subspace to compose with the full original vector. Splitting first and then applying linear function restricts the possibilities.

#### Benefits

- Allows model to attend to information from different representation subspaces
- Each head can learn different types of relationships
- Provides robustness and richer representations

---

### Positional Encodings

#### Problem Statement

**No convolution, no recurrence:** Transformer has no inherent sense of position, so we need to add positional information.

#### Mathematical Formulas

For position `pos` and dimension `i`:

```
PE(pos, 2i) = sin(pos / 10000^(2i/d_model))
PE(pos, 2i+1) = cos(pos / 10000^(2i/d_model))
```

#### Key Properties

- **Even dimensions:** Use sine function
- **Odd dimensions:** Use cosine function  
- Creates unique encoding for each position
- Allows model to learn relative positions

#### Visual Pattern

The positional encoding creates wave-like patterns across dimensions:
- Different frequencies for different dimensions
- Enables the model to distinguish between positions
- Maintains consistent mathematical relationships

---

### Feed Forward Layers

#### Mathematical Formula

```
FFN(x) = max(0, xW1 + b1)W2 + b2
```

#### Components

- **First Linear Layer:** xW1 + b1
- **ReLU Activation:** max(0, ...)
- **Second Linear Layer:** ...W2 + b2

#### Key Characteristics

- **Fully Connected Dense Layers:** For learning complex patterns
- **Individual Networks:** Each FFN is different for each layer (Nx)
- **Original Paper:** Nx = 8 (8 encoder layers, 8 decoder layers)

#### Purpose

- Processes the attention output
- Adds non-linearity to the model
- Allows for complex feature transformations

---

### Dropout

#### Application Points

**Quote from original paper:**
> "We apply dropout to the output of each sub-layer before it is added to the sub-layer and normalized. In addition, we apply dropout to the sums of embeddings and positional encodings in both encoder and decoder stacks."

#### Specific Locations

1. **Sub-layer outputs:** Before Add & Norm operations
2. **Embedding layers:** After combining embeddings with positional encodings
3. **Both stacks:** Applied in encoder and decoder

#### Purpose

- **Regularization:** Prevents overfitting
- **Robustness:** Makes model less dependent on specific neurons
- **Generalization:** Improves performance on unseen data

---

### Complete Architecture Summary

#### Encoder Stack (Nx layers)

Each encoder layer contains:
1. Multi-Head Attention
2. Add & Norm
3. Feed Forward Network  
4. Add & Norm

#### Decoder Stack (Nx layers)

Each decoder layer contains:
1. Masked Multi-Head Attention
2. Add & Norm
3. Multi-Head Attention (with encoder)
4. Add & Norm  
5. Feed Forward Network
6. Add & Norm

#### Input Processing

- **Encoder Input:** Input Embedding + Positional Encoding
- **Decoder Input:** Output Embedding (shifted right) + Positional Encoding

#### Output Generation

- **Final Processing:** Linear layer → Softmax → Output Probabilities
- **Training:** Outputs shifted right for teacher forcing
- **Inference:** Autoregressive generation

---

### Key Technical Details

#### Dimensions and Scaling

- **dk:** Dimension of key vectors
- **Scaling Factor:** √dk prevents attention weights from becoming too large
- **d_model:** Model dimension used throughout the architecture

#### Attention Types

1. **Self-Attention (Encoder):** Each position attends to all positions in input
2. **Masked Self-Attention (Decoder):** Each position attends only to earlier positions  
3. **Encoder-Decoder Attention:** Decoder attends to encoder representations

#### Training vs Inference

- **Training:** Uses teacher forcing with shifted outputs
- **Inference:** Generates tokens one by one autoregressively
- **Masking:** Ensures no information leakage from future tokens

---

### References and Additional Resources

- Original reference: http://nlp.seas.harvard.edu/2018/04/03/attention.html
- Positional encoding details: https://timodenk.com/blog/linear-relationships-in-the-transformers-positional-encoding/
- Transformer visualization: http://peterbloem.nl/blog/transformers

---

*Thank you for attending the class!*


## Lecture 9: BERT — Bidirectional Encoder Representations from Transformers

### Recap: Sequence-to-Sequence Models

Transformer architectures enable automated translation and text generation via encoder and decoder components:

- **Transformer Encoder**: Processes input data sequence (e.g., "I love llamas")
- **Transformer Decoder**: Generates output sequence; uses previously generated tokens
- **Self-Attention**: Computes context for each token
- **Feedforward Neural Networks**: Refine representations within both encoder and decoder
- **Masked Self-Attention**: Decoder only attends to known inputs and already generated outputs

---

### BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

Authors: Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova (Google AI Language)

#### Key Concepts

- **Contextualized Word Embeddings**: BERT encoder learns representations from large text corpus.
- **Bidirectional Encoding**: Encodes tokens considering both left and right context simultaneously.
- Implements only encoder and not decoder side; designed for representation, not generation.

#### Input Structure

- Special tokens: `[CLS]` for classification, `[MASK]` for masked prediction tasks
- Input sequence: `[CLS] I love llamas`
- BERT encoder applies self-attention, passing through multiple stacked layers
- Output: Contextualized word embeddings

#### Pre-training Process

1. **Masked Language Modeling (MLM):**
    - Randomly mask words in input
    - Model predicts masked words using context
2. **Next Sentence Prediction (NSP):**
    - Model learns coherence between sentence pairs

#### Fine-tuning Process

- BERT is fine-tuned for specific downstream NLP tasks with labeled datasets (e.g., classification, named entity recognition, paraphrase identification).

---

### BERT & the GLUE Benchmark

- **General Language Understanding Evaluation (GLUE):**
    - Multiple NLP tasks are evaluated using BERT embeddings and architecture
    - Example input: `[CLS] My dog is cute. [SEP] He likes playing. [SEP]`
    - Embeddings:
        - **Token Embeddings:** Learned by BERT
        - **Segment Embeddings:** Identify sentence segments
        - **Position Embeddings:** Encode position information for each token
    - Final prediction layer (classification, question answering, etc.)

#### GLUE Tasks Examples

- GLUE includes various tasks like sentence similarity, sentiment analysis, natural language inference, etc.
- Scores: Individual tasks aggregate for final GLUE score

##### BERT Training Steps for GLUE

1. **Pretrain on large unlabeled dataset (e.g., Wikipedia, Books Corpus)**
2. **Fine-tune for target tasks**
    - Each task: Supervised training with labeled dataset
    - Examples: Classification, Named Entity Recognition (NER), Paraphrase Identification

---

### Specialized BERT Models for Biomedical Domain

#### BioBERT

Original Paper: "BioBERT: a pre-trained biomedical language representation model for biomedical text mining" by Jinhyuk Lee, Wonjin Yoon, etc.

##### BioBERT Workflow

- **Pre-training:** Using biomedical corpora (PubMed abstracts, PMC full-text articles)
- **Fine-tuning:** For specific biomedical tasks (NER, Relation Extraction, Question Answering)

##### Pre-training Corpora

| Corpus                 | Number of Words | Domain      |
|------------------------|-----------------|-------------|
| English Wikipedia      | 2.5B            | General     |
| Books Corpus           | 0.8B            | General     |
| PubMed Abstracts       | 4.5B            | Biomedical  |
| PMC Full-text Articles | 13.5B           | Biomedical  |

##### Corpus Combinations

| Model                 | Corpus Combination               |
|-----------------------|----------------------------------|
| BERT (Devlin et al.)  | Wiki + Books                     |
| BioBERT (+PubMed)     | Wiki + Books + PubMed            |
| BioBERT (+PMC)        | Wiki + Books + PMC               |
| BioBERT (+PubMed+PMC) | Wiki + Books + PubMed + PMC      |

##### BioBERT Downstream Tasks

- **Named Entity Recognition**: NCBI disease, BC2GM datasets
- **Relation Extraction**: EU-ADR, ChemProt (example: "Variants in GENES contribute to DISEASES susceptibility")
- **Question Answering**: BioASQ challenge, e.g., "What does mTOR stand for?" → "Mammalian Target Of Rapamycin"

---

### Clinical Domain-Specific BERT Models

#### ClinicalBERT & Embeddings

- **ClinicalBERT**: Fine-tuned on clinical notes from MIMIC III dataset
- **Discharge Summary BERT**: Trained on hospital discharge summaries
- **Bio+Clinical BERT**: Merges biomedical and clinical corpora for pre-training
- **MedNLI, i2b2 (2006–2014)**: Used as evaluation tasks for clinical embeddings

##### Performance Snapshot

| Model                          | MedNLI | i2b2 2006 | i2b2 2010 | i2b2 2012 | i2b2 2014 |
|-------------------------------|--------|-----------|-----------|-----------|-----------|
| BERT                          | 77.6%  | 93.9      | 83.5      | 75.9      | 92.8      |
| BioBERT                       | 80.8%  | 94.8      | 86.5      | 78.9      | 93.0      |
| ClinicalBERT                  | 80.8%  | 91.5      | 86.4      | 78.5      | 92.6      |
| Discharge Summary BERT        | 80.6%  | 91.9      | 86.4      | 78.4      | 92.8      |
| Bio+Clinical BERT             | 82.7%  | 94.7      | 87.2      | 78.9      | 92.5      |
| Bio+Discharge Summary BERT    | 82.7%  | 94.8      | 87.8      | 78.9      | 92.7      |

---

### UMLS BERT — Clinical Domain Knowledge Augmentation

UmlsBERT introduces domain knowledge using UMLS (Unified Medical Language System) semantic groups:

- **Semantic Group Embeddings (SG)**: Custom embedding matrix added to BERT input to encode medical concepts
    - Example: "heart" → Anatomy
    - Each UMLS group represented by separate embedding vector
- Comparison between vanilla BERT and UmlsBERT for biomedical domain recognition, e.g., "lungs" → specific semantic group

---

### PEGASUS — Pre-training for Abstractive Summarization

Authors: Jingqing Zhang, Yao Zhao, Mohammad Saleh, Peter J. Liu

#### Core Idea

- **Gap Sentence Generation (GSG)**: Masks complete sentences, model must generate masked sentences
- **Seq2Seq Transformer Architecture**: Encoder-decoder structure for summarizing long-form text

#### Performance

- Evaluated using ROUGE scores (rouge1-F, rouge2-F, rougel-F)
- Datasets: XSum, CNN/DailyMail, WikiHow, Reddit TIFU
- Performance scales with size of training data and number of examples

##### Example: BBC News Article

- PEGASUS abstracts information (e.g., "four Royal Navy frigates") from source content listing specific ship names
- Can generate concise summaries of lengthy text content

---

### Embeddings in Biomedical NLP

#### Concept and Word Embeddings

- Various models available for biomedical and clinical data
- Embeddings support representation for any word, concept, or term
- Examples: Word2vec, GloVe, ELMO, BERT variants

| Name                              | Model               | Data/Concepts           | Terms    | Dim.   |
|------------------------------------|---------------------|-------------------------|----------|--------|
| PubMed-w2v.bin                    | word2vec            | PubMed                  | 2.4M     | 200    |
| PMC-w2v.bin                       | word2vec            | PubMed Central          | 25M      | 200    |
| PubMed-PMC-w2v.bin                | word2vec            | PubMed+PMC              | 4.1M     | 200    |
| wiki-pubmed-PMC-w2v.bin           | word2vec            | PubMed+PMC+Wikipedia    | 5.5M     | 200    |
| drug word embeddings              | word2vec            | PubMed+DrugBank         | 553195   | 420    |
| AWE-CM                            | word2vec            | UMLS CUI (concepts)     | 265M     | 300    |
| claims_codes_hs_300               | word2vec            | ICD-9 codes             | 51,327   | 300    |
| claims_cuis_hs_300                | word2vec            | UMLS CUI (concepts)     | 14,852   | 300    |
| cui2vec                           | word2vec/Glove      | UMLS CUI (concepts)     | 108,477  | 500    |
| concept embeddings                | AiTextML            | MeSH ID (concepts)      | 26,103   | 100    |
| word embeddings                   | AiTextML            | PubMed                  | 513,196  | 100    |
| ELMO (PubMed model)               | ELMO                | PubMed                  | NA       | 1024   |
| BioBERT                           | BERT                | PubMed                  | NA       | 768/1024|
| ClinicalBERT                      | BERT                | MIMIC III               | NA       | 768    |

##### Evaluation Tasks

- Word and concept similarity
- Disease prediction
- Named entity recognition
- Relation extraction
- Mortality prediction
- Readmission risk prediction
- Clinical information extraction

---

### References and Useful Links

- PEGASUS: https://ai.googleblog.com/2020/06/pegasus-state-of-art-model-for.html
- BioBERT Paper: doi: 10.1093/bioinformatics/btz682
- BioBERT Code/Data: https://github.com/dmis-lab/biobert
- Drug Word Embeddings: https://github.com/chop-dbhi/drug_word_embeddings
- Evaluation Corpora: http://evexdb.org/pmresources/

---

### Summary

BERT and its specialized extensions (BioBERT, ClinicalBERT, UmlsBERT, PEGASUS) have transformed NLP and biomedical text mining by providing powerful contextual embeddings and pre-training techniques. Fine-tuning BERT-based models on specialized corpora enables state-of-the-art performance on domain-specific tasks such as named entity recognition, relation extraction, and clinical information extraction.

