# CM3
## Table of Contents
- [CM3](#cm3)
  - [Table of Contents](#table-of-contents)
  - [Computing For Medicine Mid-Semester Examination Notes](#computing-for-medicine-mid-semester-examination-notes)
    - [Course Details and Instructions](#course-details-and-instructions)
      - [Examination Instructions](#examination-instructions)
    - [Section A (60 marks)](#section-a-60-marks)
      - [Multiple Choice Questions (4 Marks each)](#multiple-choice-questions-4-marks-each)
        - [Q1: Scaled Dot-Product Attention Formula](#q1-scaled-dot-product-attention-formula)
        - [Q2: Statements about BERT](#q2-statements-about-bert)
        - [Q3: Learning Weights in Transformers](#q3-learning-weights-in-transformers)
        - [Q4: Disadvantage of One-Hot Encoding](#q4-disadvantage-of-one-hot-encoding)
        - [Q5: CBoW vs. Skip-gram Distinction](#q5-cbow-vs-skip-gram-distinction)
        - [Q6: Primary Purpose of Positional Encoding](#q6-primary-purpose-of-positional-encoding)
        - [Q7: Purpose of the Scaling Factor in Self-Attention](#q7-purpose-of-the-scaling-factor-in-self-attention)
        - [Q8: Advantage of Residual Connections](#q8-advantage-of-residual-connections)
        - [Q9: Limitation of TF-IDF Representation](#q9-limitation-of-tf-idf-representation)
        - [Q10: Core Idea of the Distributional Hypothesis](#q10-core-idea-of-the-distributional-hypothesis)
      - [Encoding and Context Examples](#encoding-and-context-examples)
        - [Q11: One-Hot Encoding and Bag of Words Representation (4 Marks)](#q11-one-hot-encoding-and-bag-of-words-representation-4-marks)
        - [Q12: Skip-Gram Training Pairs Example (4 Marks)](#q12-skip-gram-training-pairs-example-4-marks)
      - [SNOMED CT Questions (4 Marks each)](#snomed-ct-questions-4-marks-each)
        - [Q13: Correct Statement about SNOMED CT](#q13-correct-statement-about-snomed-ct)
        - [Q14: Purpose of SNOMED CT Relationships](#q14-purpose-of-snomed-ct-relationships)
        - [Q15: Example of Post-Coordination](#q15-example-of-post-coordination)
    - [SECTION B (40 Marks)](#section-b-40-marks)
      - [Q1: Integrating Transformer Models with UMLS for Clinical Decision Support (10 Marks)](#q1-integrating-transformer-models-with-umls-for-clinical-decision-support-10-marks)
        - [1. Context and Rationale](#1-context-and-rationale)
        - [2. Integration for Clinical Decision Support (CDS)](#2-integration-for-clinical-decision-support-cds)
        - [3. Illustration Example](#3-illustration-example)
        - [4. Methods of Integration](#4-methods-of-integration)
        - [5. Integration within the Standard Transformer Block Structure](#5-integration-within-the-standard-transformer-block-structure)
        - [6. Benefits for Clinical Decision Support](#6-benefits-for-clinical-decision-support)
      - [Q2: Positional Encoding and Look-Ahead Masking (10 Marks)](#q2-positional-encoding-and-look-ahead-masking-10-marks)
        - [1. Positional Encoding (PE)](#1-positional-encoding-pe)
        - [2. Look-ahead Masking](#2-look-ahead-masking)
      - [Q3: Comparison of Skip-Gram and Continuous Bag of Words (CBOW) (10 Marks)](#q3-comparison-of-skip-gram-and-continuous-bag-of-words-cbow-10-marks)
        - [1. Comparison Table](#1-comparison-table)
        - [2. Conceptual Difference](#2-conceptual-difference)
        - [3. Toy Example: Clinical Sentence (Training Pairs Generation)](#3-toy-example-clinical-sentence-training-pairs-generation)
      - [Q4: Ethics and Challenges of Sharing Deidentified Data (10 Marks)](#q4-ethics-and-challenges-of-sharing-deidentified-data-10-marks)
        - [Why Sharing Deidentified Data Like MIMIC Freely is Risky](#why-sharing-deidentified-data-like-mimic-freely-is-risky)
        - [1. Risks of Sharing Deidentified Data](#1-risks-of-sharing-deidentified-data)
        - [2. Challenges in the Era of Large Language Models (LLMs)](#2-challenges-in-the-era-of-large-language-models-llms)
        - [3. Best Practices for Handling MIMIC and Similar Data](#3-best-practices-for-handling-mimic-and-similar-data)
        - [Conclusion](#conclusion)
  - [Assignment 1: FHIR Storyboarding](#assignment-1-fhir-storyboarding)
    - [Predictive Feature Set Exchange for Shock](#predictive-feature-set-exchange-for-shock)
    - [Table of Contents](#table-of-contents-1)
  - [Predictive Feature Set Exchange for Shock](#predictive-feature-set-exchange-for-shock-1)
    - [1. Problem Selection](#1-problem-selection)
      - [Scenario: Emergency Shock Prediction in Intensive Care](#scenario-emergency-shock-prediction-in-intensive-care)
      - [Problem Description](#problem-description)
      - [Goal](#goal)
    - [2. FHIR Resource Selection](#2-fhir-resource-selection)
    - [3. Archetype Profiling (ShockModes Feature Set Profile)](#3-archetype-profiling-shockmodes-feature-set-profile)
      - [Profile Name](#profile-name)
      - [Constraints Applied to Observation Resource](#constraints-applied-to-observation-resource)
        - [Mandating Derived Feature Codes](#mandating-derived-feature-codes)
        - [Time-Series Context (`effectivePeriod`)](#time-series-context-effectiveperiod)
        - [Value Standardization (`valueQuantity`)](#value-standardization-valuequantity)
        - [Provenance and Source (`derivedFrom`)](#provenance-and-source-derivedfrom)
      - [FHIR Data Exchange Flow for ShockModes Predictive Feature Set](#fhir-data-exchange-flow-for-shockmodes-predictive-feature-set)
    - [4. FHIR-Compliant JSON Resource Examples](#4-fhir-compliant-json-resource-examples)
      - [Patient Resource json](#patient-resource-json)
      - [ShockModes Feature Observation Resource json](#shockmodes-feature-observation-resource-json)
      - [MedicationAdministration Resource json](#medicationadministration-resource-json)
      - [Procedure Resource json](#procedure-resource-json)
      - [Encounter Resource json](#encounter-resource-json)
    - [5. Result](#5-result)
      - [Enables Predictive AI Exchange](#enables-predictive-ai-exchange)
      - [Achieves Semantic Interoperability for Features](#achieves-semantic-interoperability-for-features)
      - [Improves Clinical Workflow and Patient Safety](#improves-clinical-workflow-and-patient-safety)
      - [Establishes Data Provenance and Clinical Trust](#establishes-data-provenance-and-clinical-trust)
      - [Supports Multimodal AI Integration](#supports-multimodal-ai-integration)
    - [6. References](#6-references)
  - [Computing for Medicine Lecture 10: Storyboarding, HL7 \& FHIR](#computing-for-medicine-lecture-10-storyboarding-hl7--fhir)
    - [Step 1: Define the Purpose, Gather the Requirements and Storyboard the Experience](#step-1-define-the-purpose-gather-the-requirements-and-storyboard-the-experience)
      - [Storyboarding Saves Lives!](#storyboarding-saves-lives)
    - [Step 2: Create a Conceptual Model](#step-2-create-a-conceptual-model)
      - [What is a Model and a Meta-Model?](#what-is-a-model-and-a-meta-model)
        - [Types of Meta- Models](#types-of-meta--models)
      - [System, Use cases, Actors, Scenarios](#system-use-cases-actors-scenarios)
      - [Modeling Components and Diagrams](#modeling-components-and-diagrams)
    - [Step 3: Choose a Technical Framework, e.g. FHIR](#step-3-choose-a-technical-framework-eg-fhir)
      - [Technical Interoperability: The Technology Layer](#technical-interoperability-the-technology-layer)
      - [Health Level 7 International (HL7)](#health-level-7-international-hl7)
      - [Sequential Steps in Object Oriented Software Development](#sequential-steps-in-object-oriented-software-development)
      - [HL7 Standard and Messages](#hl7-standard-and-messages)
      - [Core Idea: REST (Representational State Transfer)](#core-idea-rest-representational-state-transfer)
    - [FHIR Scope, Modeling, and Resources](#fhir-scope-modeling-and-resources)
      - [FHIR Scope of Models: General to Specific](#fhir-scope-of-models-general-to-specific)
      - [Reference Information Model (RIM): General Scope](#reference-information-model-rim-general-scope)
        - [Tying the RIM to the Storyboarding](#tying-the-rim-to-the-storyboarding)
        - [List out the objects at RIM level (Abstract Example)](#list-out-the-objects-at-rim-level-abstract-example)
        - [Python code stub for RIM (Abstract Classes)](#python-code-stub-for-rim-abstract-classes)
      - [Refined Message Information Model (RMIM): Specific](#refined-message-information-model-rmim-specific)
        - [List out the details at RMIM level (Specific Example)](#list-out-the-details-at-rmim-level-specific-example)
        - [Python code stub for RMIM](#python-code-stub-for-rmim)
    - [Deep Dive into FHIR](#deep-dive-into-fhir)
      - [FHIR Resources and Conformance](#fhir-resources-and-conformance)
      - [Value Sets \& Profiles](#value-sets--profiles)
        - [Example Value Set for Gender (JSON Format)](#example-value-set-for-gender-json-format)
      - [Implementation and Real-World Examples](#implementation-and-real-world-examples)
        - [India's FHIR Stack (ABDM)](#indias-fhir-stack-abdm)
      - [Steps for FHIR System Building](#steps-for-fhir-system-building)
  - [Computing for Medicine Lecture 11: HL7 \& FHIR Notes](#computing-for-medicine-lecture-11-hl7--fhir-notes)
    - [Technical Framework and Interoperability](#technical-framework-and-interoperability)
      - [Step 3: Choose a Technical Framework, e.g. FHIR](#step-3-choose-a-technical-framework-eg-fhir-1)
      - [Technical Interoperability: The Technology Layer](#technical-interoperability-the-technology-layer-1)
      - [Data Flow and Software Development Steps](#data-flow-and-software-development-steps)
    - [Health Level 7 International (HL7)](#health-level-7-international-hl7-1)
      - [Syntactic Interoperability: HL7 Standard](#syntactic-interoperability-hl7-standard)
    - [FHIR Standard and REST](#fhir-standard-and-rest)
      - [HL7 Messages](#hl7-messages)
      - [Core Idea: REST (Representational State Transfer)](#core-idea-rest-representational-state-transfer-1)
      - [Deep Dive into FHIR Resources](#deep-dive-into-fhir-resources)
    - [FHIR Scope of Models: General to Specific](#fhir-scope-of-models-general-to-specific-1)
    - [Reference Information Model (RIM)](#reference-information-model-rim)
      - [RIM Details](#rim-details)
      - [Tying the RIM to Storyboarding](#tying-the-rim-to-storyboarding)
        - [Objects at RIM Level](#objects-at-rim-level)
    - [Refined Message Information Model (RMIM)](#refined-message-information-model-rmim)
        - [Details at RMIM Level (Example)](#details-at-rmim-level-example)
      - [Python Code Stub for RIM and RMIM](#python-code-stub-for-rim-and-rmim)
        - [HL7 v3 RIM Abstract Classes](#hl7-v3-rim-abstract-classes)
        - [RMIM Classes and Functions](#rmim-classes-and-functions)
    - [FHIR Conformance and Resources](#fhir-conformance-and-resources)
      - [Conformance, Value Sets \& Profiles](#conformance-value-sets--profiles)
        - [Value Set Example](#value-set-example)
        - [Profiles](#profiles)
      - [Example: Patient Resource](#example-patient-resource)
      - [Openly Available FHIR Servers and Hands On](#openly-available-fhir-servers-and-hands-on)
    - [Real-World Implementations](#real-world-implementations)
      - [India on FHIR (ABDM)](#india-on-fhir-abdm)
      - [Other Implementations](#other-implementations)
      - [General Implementation Steps](#general-implementation-steps)
  - [Computing for Medicine Lecture 12: FHIR and Analytics](#computing-for-medicine-lecture-12-fhir-and-analytics)
    - [1. FHIR Resource Example: Patient Resource](#1-fhir-resource-example-patient-resource)
      - [Summary of the Patient Resource](#summary-of-the-patient-resource)
      - [Example JSON for the Patient Resource](#example-json-for-the-patient-resource)
    - [2. FHIR Scope of Models: General to Specific](#2-fhir-scope-of-models-general-to-specific)
    - [3. Reference Information Model (RIM)](#3-reference-information-model-rim)
      - [Reference Information Model: General Scope](#reference-information-model-general-scope)
    - [4. Tying the RIM to Storyboarding](#4-tying-the-rim-to-storyboarding)
      - [List out the objects at RIM level](#list-out-the-objects-at-rim-level)
      - [Python code stub for RIM](#python-code-stub-for-rim)
    - [5. Refined Message Information Model (RMIM)](#5-refined-message-information-model-rmim)
      - [Refined Message Information Model: Specific](#refined-message-information-model-specific)
      - [List out the details at RMIM level](#list-out-the-details-at-rmim-level)
      - [RMIM Python Code](#rmim-python-code)
    - [6. FHIR Implementation and Analytics](#6-fhir-implementation-and-analytics)
      - [Openly Available FHIR Servers](#openly-available-fhir-servers)
      - [Hands On](#hands-on)
      - [Real World Implementations of FHIR Resources](#real-world-implementations-of-fhir-resources)
        - [India's FHIR Stack (ABDM)](#indias-fhir-stack-abdm-1)
        - [Google on FHIR](#google-on-fhir)
        - [UK Implementation](#uk-implementation)
        - [UCSF Use of AWS APIs for FHIR](#ucsf-use-of-aws-apis-for-fhir)
        - [FHIR Capabilities](#fhir-capabilities)
    - [7. SMART on FHIR](#7-smart-on-fhir)
      - [Definition and Function](#definition-and-function)
      - [What SMART Does](#what-smart-does)
      - [Applications and Regulatory Use](#applications-and-regulatory-use)
    - [8. Prior Authorization Reform in US CMS (MEDICAID)](#8-prior-authorization-reform-in-us-cms-medicaid)


## Computing For Medicine Mid-Semester Examination Notes

### Course Details and Instructions

*   **Course Name:** Computing For Medicine
*   **Course Codes:** CSE585/BIO546
*   **Examination Type:** Mid Semester Examination

#### Examination Instructions

1.  **Exam Duration:** 1 hour.
2.  **Maximum Marks:** 100.
3.  **Multiple Choice Questions (MCQs):** Only one option in MCQs is correct.
4.  **Submission:** MCQs have to be submitted on the Answer Sheet; responses marked on the Question Paper will **NOT** be considered.

### Section A (60 marks)

#### Multiple Choice Questions (4 Marks each)

##### Q1: Scaled Dot-Product Attention Formula

Which of the following correctly represents the formula for scaled dot-product attention (ignoring bias terms)?

**d) Softmax(QKT/$\sqrt{d_k}$)V**

##### Q2: Statements about BERT

Which of the following is **NOT true** about BERT?

**c) BERT processes tokens strictly in a left-to-right autoregressive manner during pretraining.**

*   *Note:* The following statements *are* true about BERT:
    *   BERT representations can be transferred to downstream NLP tasks with minimal task-specific architecture changes.
    *   BERT can be fine-tuned for tasks such as text classification, question answering, and named entity recognition.
    *   BERT’s architecture allows contextual embeddings where the same word can have different vector representations depending on surrounding context.

##### Q3: Learning Weights in Transformers

What in Transformers directly enables learning of weights?

**b) Feed-forward layer**
**c) Multi-head Attention**

*Note: Both b and c are listed as correct options in the source.*

##### Q4: Disadvantage of One-Hot Encoding

Which of the following is a disadvantage of one-hot encoding for medical text data?

**b) It results in extremely high-dimensional sparse vectors, making computation and storage inefficient.**

##### Q5: CBoW vs. Skip-gram Distinction

Which of the following statements correctly distinguishes the Continuous Bag-of-Words (CBoW) model from the Skip-gram model in word2vec architecture?

**c) CBoW is trained to predict surrounding the middle word given a context while Skip-gram predicts context given the middle word.**

##### Q6: Primary Purpose of Positional Encoding

In Transformers, what is the primary purpose of **positional encoding**?

**d) To provide information about the order of tokens in a sequence**

##### Q7: Purpose of the Scaling Factor in Self-Attention

In the self-attention mechanism, what is the purpose of the scaling factor $1/\sqrt{d_k}$ (represented as $1dk$ in the source) in the attention computation?

**b) To normalize the dot products and prevent extremely large values before softmax**

##### Q8: Advantage of Residual Connections

The primary advantage of using residual connections (skip connections) in deep neural networks is to …

**a) prevent vanishing gradients during backpropagation**

##### Q9: Limitation of TF-IDF Representation

Which of the following is a limitation of TF-IDF representation?

**c) It fails to capture semantic similarity between documents**

##### Q10: Core Idea of the Distributional Hypothesis

Based on the "Vector Space Paradigm: Distributional Hypothesis," what is the core idea behind modern word representations?

**b. The meaning of a word is determined by the words that surround it.**

#### Encoding and Context Examples

##### Q11: One-Hot Encoding and Bag of Words Representation (4 Marks)

**Given Data:**
*   **Vocabulary:** `{ "the": 0, "cat": 1, "sat": 2, "on": 3, "mat: 4, "dog": 5, "barked": 6 }`
*   **Sentence:** `“dog barked on cat”`

**Representations:**

| Word | One-Hot Encoding (per word) |
| :--- | :-------------------------- |
| dog | `` |
| barked | `` |
| on | `` |
| cat | `` |

**Bag of Words vector for whole sentence:**
``

##### Q12: Skip-Gram Training Pairs Example (4 Marks)

**Scenario:**
*   **Sentence:** `"the quick brown fox jumps over the lazy dog"`
*   **Model:** Skip-Gram
*   **Context Window Size:** 3

**Training Pairs (target → context) where the target word is "fox":**

*   **Context:** `{quick, brown, the, jumps, over}`
*   **Total Pairs:** 5 pairs total.

| Target | Context Word |
| :----- | :----------- |
| (fox, | the) |
| (fox, | quick) |
| (fox, | brown) |
| (fox, | jumps) |
| (fox, | over) |

#### SNOMED CT Questions (4 Marks each)

##### Q13: Correct Statement about SNOMED CT

In SNOMED CT, which statement is correct?

**c. Every concept has a unique, language-independent identifier and is linked to multiple descriptions.**

##### Q14: Purpose of SNOMED CT Relationships

In SNOMED CT, relationships such as “finding site” or “causative agent” are used to:

**b. Link concepts into a computable ontology that supports clinical reasoning.**

##### Q15: Example of Post-Coordination

Which of the following is an example of post-coordination in SNOMED CT?

**Linking two concepts such as Type 2 Diabetes Mellitus and Increased Urination Frequency, using a relationship to express a combined clinical idea.**

### SECTION B (40 Marks)

#### Q1: Integrating Transformer Models with UMLS for Clinical Decision Support (10 Marks)

##### 1. Context and Rationale

**Transformer-based language models** (e.g., BERT or GPT) are adept at understanding contextual relationships in text. In clinical settings, they can process electronic health records (EHRs), clinical notes, and research articles.

However, purely data-driven models may miss **domain-specific medical knowledge**, potentially leading to incorrect or incomplete recommendations.

**The UMLS (Unified Medical Language System) thesaurus** is a **curated ontology** that contains:
*   Medical concepts (CUIs).
*   Synonyms.
*   Relationships between concepts.

Integrating UMLS with Transformers helps models understand and leverage **structured clinical knowledge** alongside unstructured text. This enhances Clinical Decision Support (CDS) by leading to more accurate diagnoses, treatment suggestions, and risk predictions.

##### 2. Integration for Clinical Decision Support (CDS)

By incorporating UMLS, transformers achieve better outcomes:

*   **Mapping:** Transformers can better **map clinical terms to standardized medical concepts** (e.g., mapping “high blood sugar” to “Hyperglycemia”).
*   **Reasoning:** This allows the model to reason not only on linguistic context but also on **domain knowledge**.
*   **Improvement:** This leads to improved clinical entity recognition, relation extraction, and decision support tasks (e.g., diagnosis suggestions).
*   **Benefits:** The enriched model can reduce ambiguity, handle synonyms, and improve interpretability in CDS systems.

##### 3. Illustration Example

| Input Text | Mapped Concepts | Impact | Output Prediction |
| :--- | :--- | :--- | :--- |
| Clinical Note Text: "Patient has high blood sugar and frequent urination." | Mapped UMLS Concepts: Hyperglycemia (C0011849), Polyuria (C0034000) | **Attention Layer:** Increase interaction between "high blood sugar" and "frequent urination" based on UMLS relation. | Transformer predicts Type 2 Diabetes Mellitus with higher confidence, leveraging both textual context and UMLS knowledge. |

**Conceptual Embeddings:**
*   **Word embeddings:** `["Patient", "has", "high", "blood", "sugar", ...]`
*   **Concept embeddings:** `[C0011849, C0034000]`

##### 4. Methods of Integration

**a) Concept Embedding Augmentation:**
1.  Clinical text is first mapped to UMLS concepts using a tool like MetaMap or QuickUMLS.
2.  Each concept is converted into an **embedding vector**, representing its meaning in a structured space.
3.  During training or inference, the Transformer receives both **word embeddings and concept embeddings**, enriching its understanding of medical terminology.

**b) Knowledge Graph Encoding:**
1.  UMLS contains relationships between concepts (e.g., “causes,” “treats,” “associated with”).
2.  These relationships can be encoded as a knowledge graph.
3.  **Graph embeddings** of connected concepts can be injected into the Transformer's attention layers, guiding the model to pay attention to medically relevant associations.

**c) Attention Biasing using UMLS:**
*   UMLS relationships can **bias the Transformer's self-attention mechanism**, increasing attention weights between words that correspond to related medical concepts.
*   *Example:* If the note mentions “hyperglycemia” and “insulin,” UMLS relationships inform the model that these are strongly related, allowing better context propagation in the Transformer layers.

##### 5. Integration within the Standard Transformer Block Structure

A standard Transformer block sequence is: Multi-Head Self-Attention → Add & Norm → Feed-Forward → Add & Norm.

**UMLS Integration Points:**

1.  **Input Layer Integration:** Combine word embeddings with UMLS concept embeddings as the initial input to the Transformer. This allows the model to understand both linguistic and medical knowledge from the first layer.

2.  **Attention Layer Integration:** Modify the attention scores using UMLS knowledge. For tokens mapped to related concepts, attention weights are increased proportionally to the strength of their relationship in UMLS. This ensures medically related terms interact more strongly during contextual encoding.

3.  **Intermediate Fusion Layers:** Inject UMLS knowledge embeddings into the feed-forward layers as side inputs. This helps the model combine learned linguistic patterns with curated medical knowledge before producing final outputs.

**Illustration in Block Structure:**
*   **Input =** `[Word Embedding + Position Encoding + UMLS Concept Embedding]`
*   **Transformer Encoder Layers =** `Self-Attention (uses both text + concept similarity) → Feed Forward → Normalization`
*   **Output =** `Knowledge-enriched representation mapped to CDS task (diagnosis, drug recommendation, etc.)`

##### 6. Benefits for Clinical Decision Support

Integrating UMLS into transformers creates a **knowledge-enhanced model** that combines contextual understanding with domain-specific semantics.

1.  Improves diagnosis suggestions by connecting symptoms to related conditions.
2.  Enhances treatment recommendations using concept relationships (drug-disease interactions).
3.  Reduces ambiguity in medical language, handling synonyms, abbreviations, and variations in terminology.
4.  Facilitates explainable AI, as UMLS relationships can justify why the model made certain recommendations.

---

#### Q2: Positional Encoding and Look-Ahead Masking (10 Marks)

##### 1. Positional Encoding (PE)

**Concept Definition:**
Transformers process all tokens in a sequence simultaneously, meaning they do not have a built-in notion of word order. **Positional encoding** is added to the input embeddings to provide information about the position of each token in the sequence.

**Mechanism:**
PE encodes position information using **sinusoidal functions** (sine and cosine) or learned embeddings.

**Necessity:**
Positional encoding is necessary because the Transformer relies purely on **self-attention mechanisms**, which do not inherently capture the sequential order of tokens. Unlike RNNs and CNNs that naturally handle sequential information, attention-based models process all tokens in parallel. PE provides each token with information about its position, enabling the model to capture the order of tokens and effectively learn relationships between them in a context-aware way.

**Sinusoidal Functions:**
For each token position `pos` and for each dimension `i` in the positional encoding vector, the encoding is calculated using:

$$
PE(pos, 2i) = \sin(\frac{pos}{10000^{2i/d_{\text{model}}}})
$$

$$
PE(pos, 2i+1) = \cos(\frac{pos}{10000^{2i/d_{\text{model}}}})
$$

*   `pos` represents the position of the token.
*   `i` represents the dimension.
*   The use of different frequencies (scaling the position with exponential powers of 10,000) allows the model to capture relative position information across different dimensions.
*   The sine and cosine values at different frequencies help encode position information such that any offset between two positions can be computed linearly, aiding the model in learning relative distances between tokens.

**Purpose:**
PE helps the model understand word order, which is crucial in language tasks (e.g., “The cat chased the dog” vs. “The dog chased the cat”).

*   *Example:* For the sentence “Patient has fever,” positional encoding tells the model that “Patient” comes first, “has” second, and so on, even though all tokens are processed in parallel.

##### 2. Look-ahead Masking

**Concept Definition:**
**Look-ahead masking** is used in the **decoder** during training to prevent the model from “seeing” future tokens when predicting the next token.

**Why it is needed:**
Transformers use self-attention, allowing every token to look at all other tokens to gather context. While this is effective for understanding text all at once, it is problematic for language generation, where tokens are predicted one at a time (causal generation).

**Purpose/Preventing Cheating:**
*   The mask prevents a token from “seeing” future tokens.
*   If the model could see future words during training, it would “cheat,” learning from answers it shouldn’t know yet.
*   Look-ahead masking ensures the model predicts the next word based only on previous words.

**Example Scenario:**

*   *Input:* `I love to ___ pizza`
*   *Issue:* Without masking, the model could see "eat" in the future and just copy it, instead of learning proper patterns.

*   *Example Sentence:* `["Patient", "has", "fever"]`
    *   To predict “Patient”, it sees only itself.
    *   To predict “has”, it can see “Patient” but not “fever”.
    *   To predict “fever”, it can see “Patient” and “has,” but nothing beyond.

**Implementation:**
The mask is applied as a **triangular matrix** where entries above the diagonal are blocked. This ensures no future information leaks.

**Location:**
Look-ahead masking is applied in the **decoder** during training. The attention layer in the decoder uses this mask to block information from future words. This helps the model learn causal relationships: what comes next depends only on what has already happened.

---

#### Q3: Comparison of Skip-Gram and Continuous Bag of Words (CBOW) (10 Marks)

Word2Vec creates vector representations of words such that words appearing in similar contexts get similar vectors.

##### 1. Comparison Table

| Feature | CBOW | Skip-Gram |
| :--- | :--- | :--- |
| **Goal** | Predict the target word from surrounding context words | Predict surrounding context words from the target word |
| **Input** | Context words (words around the target) | Single target word |
| **Output** | Target word | Context words |
| **Training** | Faster | Slower |
| **Used case** | Capturing general semantic meaning | Capturing richer relationships, especially for rare terms |

##### 2. Conceptual Difference

*   **CBOW:** Looks at the surrounding words and tries to guess the word in the middle. (Guess the missing word from neighbors).
*   **Skip-Gram:** Takes the middle word and tries to guess the words around it. (Guess neighbors from this word).

##### 3. Toy Example: Clinical Sentence (Training Pairs Generation)

**Sentence:** `"Patient shows high blood pressure"`
**Context window:** 2 words on each side (total window size = 5)

| Architecture | Training Pairs (Input → Output) |
| :--- | :--- |
| **CBOW (context → target):** | Context: `"Patient"`, `"shows"` → Target: `"high"` |
| | Context: `"shows"`, `"high"` → Target: `"blood"` |
| | Context: `"high"`, `"blood"` → Target: `"pressure"` |
| **Skip-Gram (target → context):** | Target: `"high"` → Context: `"Patient"`, `"shows"`, `"blood"`, `"pressure"` |
| | Target: `"blood"` → Context: `"shows"`, `"high"`, `"pressure"` |

---

#### Q4: Ethics and Challenges of Sharing Deidentified Data (10 Marks)

##### Why Sharing Deidentified Data Like MIMIC Freely is Risky

MIMIC (Medical Information Mart for Intensive Care) is a widely used clinical dataset containing detailed patient information from ICU stays. Even though it is deidentified, it still contains sensitive information about real patients’ diagnoses, treatments, and outcomes. Copying such data onto pen drives or sharing via cloud platforms like Google Drive is not advisable, as it leads to serious ethical, legal, and technical consequences.

##### 1. Risks of Sharing Deidentified Data

**Reidentification Risk:**
*   Deidentification removes direct identifiers (names, addresses, phone numbers).
*   However, **quasi-identifiers** (like age, gender, admission date, or rare diagnoses) can still be used to reidentify patients.
*   Advanced techniques and cross-referencing with publicly available data can sometimes reveal patient identities.

**Violation of Data Use Agreements (DUAs):**
*   Access to MIMIC data is granted only after signing a DUA, which strictly prohibits unauthorized sharing.
*   Sharing data on unsecured platforms like pen drives or Google Drive breaches these agreements, potentially resulting in loss of access, legal action, or institutional penalties.

**Ethical Responsibility:**
*   Anonymized data represents real patient experiences.
*   Researchers have a duty to handle such data securely and ensure it is used only for approved research purposes.

##### 2. Challenges in the Era of Large Language Models (LLMs)

The advent of LLMs introduces specific risks when handling sensitive datasets:

**Increased Reidentification Risk via LLMs:**
*   Modern LLMs can process and memorize large amounts of data.
*   If sensitive clinical datasets are uploaded or shared insecurely, LLMs could inadvertently learn or leak patient-specific information.
*   Even anonymized text may contain patterns that LLMs can exploit to reconstruct private information.

**Large Context Windows:**
*   LLMs can process long sequences of text.
*   This means more information from the dataset can be exposed in one go, increasing the chance of privacy breaches if shared outside secure environments.

**Data Leakage Through Collaboration Tools:**
*   Cloud services, email, or shared drives may have weak security, making them vulnerable to unauthorized access or hacking.
*   Once clinical data leaves a controlled environment, it is almost impossible to guarantee its security.

##### 3. Best Practices for Handling MIMIC and Similar Data

Researchers must follow guidelines to protect patient privacy:

1.  Use secure institutional servers with controlled access for storing and processing data.
2.  Follow the MIMIC Data Use Agreement strictly.
3.  Share only derived results or aggregate statistics, not raw patient-level data.
4.  Avoid uploading sensitive data to external services, including Google Drive, unless encrypted and approved by the institution.

##### Conclusion

Even deidentified datasets like MIMIC cannot be treated as completely risk-free. Simply copying them to a pen drive or sharing via Google Drive is unsafe, unethical, and often illegal. The capability of LLMs to process large contexts and potentially memorize sensitive details amplifies the risks of reidentification and data leakage. Responsible handling, secure storage, and adherence to legal and ethical guidelines are essential for protecting patient privacy while enabling research.

## Assignment 1: FHIR Storyboarding

### Predictive Feature Set Exchange for Shock

*Name: Siddhant Bali (2022496) Date: 26 October 2025*

***

### Table of Contents

1. Problem Selection
2. FHIR Resource Selection
3. Archetype Profiling (ShockModes Feature Set Profile)
4. FHIR-Compliant JSON Resource Examples
5. Result
6. References

***

## Predictive Feature Set Exchange for Shock

### 1. Problem Selection

#### Scenario: Emergency Shock Prediction in Intensive Care

The scenario involves **Rajesh Kumar**, a 52-year-old construction worker from Delhi. He is admitted to the ICU at AIIMS following complications from pneumonia. Although his condition appears stable initially with normal vital signs, patients with his profile face a risk of developing circulatory shock within the next 24 hours.

The **ShockModes predictive model** requires complex, multimodal feature sets derived from continuous physiological measurements and clinical interventions to predict shock 24 hours in advance with high accuracy.

#### Problem Description

The raw high-frequency time-series data (such as Heart Rate, Systolic Blood Pressure, and Respiratory Rate) and the necessary derived statistical features (e.g., time-series entropy, Fourier coefficients) must be exchanged efficiently between the ICU's EHR system and the external AI service running the ShockModes model.

Standard clinical FHIR resources alone are **insufficient** for conveying these complex derived features. These features serve as input vectors for the machine learning algorithm. This algorithm can predict abnormal Shock Index (SI ≥ 0.7) with **83% sensitivity** and **94% specificity**.

#### Goal

The goal is to **define a FHIR profile** that standardizes the packaging and exchange of this critical, multimodal feature set to enable 24-hour advance prediction of circulatory shock in ICU patients like Rajesh.

### 2. FHIR Resource Selection

The exchange of multimodal features for shock prediction requires resources that capture physiological measurements, therapeutic interventions, and clinical procedures.

| FHIR Resource Category | Resource Name | Purpose in Scenario |
| :--- | :--- | :--- |
| Clinical | **Observation** | This is the primary resource for carrying both raw vital signs (time-series) and derived statistical features (e.g., HR Time Series Entropy, SBP FFT coefficients) needed by the ShockModes model. |
| Clinical | **MedicationAdministration** | Documents specific therapeutic interventions (e.g., heparin sodium prophylaxis) which serve as critical input features for the prediction model. |
| Clinical | **Procedure** | Documents invasive procedures (e.g., mechanical ventilation, intubation) that are essential binary features for shock prediction. |
| Administration | **Patient** | Identifies the subject of the prediction cohort—Rajesh Kumar and his demographic information. |
| Conformance | **StructureDefinition** | Defines the constraints applied to the Observation resource (the ShockModes Profile). |

### 3. Archetype Profiling (ShockModes Feature Set Profile)

To handle the complexity of time-series data processed by tools like `tsfresh` (which extracts **3,117 features**), the core FHIR Observation resource must be constrained using a Profile.

#### Profile Name

`ShockModesFeatureSetObservation`

#### Constraints Applied to Observation Resource

##### Mandating Derived Feature Codes

*   **Constraint:** The `Observation.code` element must use structured terminology representing derived statistical features rather than simple measurements.
*   **Example Code:** Instead of basic LOINC for 'Heart Rate', the code must represent features such as `RR_TS_ENTROPY` or `SBP_FFT_coefficient_abs_coeff_40`.
*   **Rationale:** This enforces semantic interoperability for the specific feature set required by ShockModes.

##### Time-Series Context (`effectivePeriod`)

*   **Constraint:** The `effectivePeriod` must be mandatory, strictly defining the **24-hour time window** over which raw physiological data was collected and features computed.
*   **Rationale:** This is critical for predicting shock events 24 hours in advance with proper temporal context.

##### Value Standardization (`valueQuantity`)

*   **Constraint:** The `valueQuantity` element is mandatory and must carry the numerical output of the feature extraction calculation (e.g., entropy scores, Fourier coefficients).
*   **Rationale:** This ensures consistent numerical representation of complex statistical features.

##### Provenance and Source (`derivedFrom`)

*   **Constraint:** The Observation must link back (via `derivedFrom` reference) to the raw, underlying high-frequency Observation resources.
*   **Rationale:** This supports **FAIR principles** of data reusability and provides traceability for clinical validation.

***

#### FHIR Data Exchange Flow for ShockModes Predictive Feature Set

(This section introduces the flow, demonstrated by the following JSON examples).

### 4. FHIR-Compliant JSON Resource Examples

These examples show customized FHIR resources carrying the high-impact statistical features derived from Rajesh Kumar's vitals, ready for consumption by the ShockModes predictive model.

#### Patient Resource json

```json
{
  "resourceType": "Patient",
  "id": "rajesh-kumar-icu",
  "name": [
    {
      "use": "official",
      "family": "Kumar",
      "given": ["Rajesh"]
    }
  ],
  "gender": "male",
  "birthDate": "1972-03-15",
  "address": [
    {
      "use": "home",
      "city": "Delhi",
      "state": "Delhi",
      "country": "IN"
    }
  ],
  "telecom": [
    {
      "system": "phone",
      "value": "+91-9876543210"
    }
  ],
  "contact": [
    {
      "relationship": [{ "coding": [{ "code": "E" }] }],
      "name": { "text": "Priya Kumar" },
      "telecom": [{ "system": "phone", "value": "+91-9876543211" }]
    }
  ]
}
```

#### ShockModes Feature Observation Resource json

This example shows the Respiratory Rate Time Series Entropy feature.

```json
{
  "resourceType": "Observation",
  "id": "rr-entropy-feature-rajesh",
  "meta": {
    "profile": [
      "http://example.org/StructureDefinition/ShockModesFea tureSetObservation"
    ]
  },
  "status": "final",
  "category": [
    {
      "coding": [
        {
          "system": "http://terminology.hl7.org/CodeSystem/observation-ca tegory",
          "code": "survey",
          "display": "Survey"
        }
      ]
    }
  ],
  "code": {
    "coding": [
      {
        "system": "http://custom-terminology.org/shockmodes-features",
        "code": "RR_TS_ENTROPY",
        "display": "Respiratory Rate Time Series Entropy"
      }
    ]
  },
  "subject": {
    "reference": "Patient/rajesh-kumar-icu"
  },
  "effectivePeriod": {
    "start": "2025-10-26T08:00:00+05:30",
    "end": "2025-10-27T08:00:00+05:30"
  },
  "valueQuantity": {
    "value": 0.987,
    "unit": "unitless",
    "system": "http://unitsofmeasure.org",
    "code": "{score}"
  },
  "derivedFrom": [
    {
      "reference": "Observation/raw-rr-time-series-rajesh"
    }
  ],
  "note": [
    {
      "text": "Feature extracted using tsfresh library from 24h respiratory rate monitoring window."
    }
  ]
}
```

#### MedicationAdministration Resource json

This example documents heparin sodium prophylaxis.

```json
{
  "resourceType": "MedicationAdministration",
  "id": "heparin-prophylaxis-rajesh",
  "status": "completed",
  "medicationCodeableConcept": {
    "coding": [
      {
        "system": "http://www.nlm.nih.gov/research/umls/rxnorm",
        "code": "5224",
        "display": "Heparin Sodium"
      }
    ]
  },
  "subject": {
    "reference": "Patient/rajesh-kumar-icu"
  },
  "effectivePeriod": {
    "start": "2025-10-26T10:00:00+05:30",
    "end": "2025-10-26T10:05:00+05:30"
  },
  "dosage": {
    "text": "5000 units subcutaneous prophylaxis",
    "dose": {
      "value": 5000,
      "unit": "units",
      "system": "http://unitsofmeasure.org",
      "code": "[iU]"
    }
  },
  "note": [
    {
      "text": "Prophylactic heparin administration - key feature for ShockModes prediction model."
    }
  ]
}
```

#### Procedure Resource json

This example documents mechanical ventilation.

```json
{
  "resourceType": "Procedure",
  "id": "mechanical-ventilation-rajesh",
  "status": "in-progress",
  "code": {
    "coding": [
      {
        "system": "http://snomed.info/sct",
        "code": "40617009",
        "display": "Artificial ventilation"
      }
    ]
  },
  "subject": {
    "reference": "Patient/rajesh-kumar-icu"
  },
  "performedPeriod": {
    "start": "2025-10-26T09:30:00+05:30"
  },
  "note": [
    {
      "text": "Mechanical ventilation initiated due to respiratory distress - critical binary feature for shock prediction."
    }
  ]
}
```

#### Encounter Resource json

This example documents the ICU admission.

```json
{
  "resourceType": "Encounter",
  "id": "icu-admission-rajesh",
  "status": "in-progress",
  "class": {
    "system": "http://terminology.hl7.org/CodeSystem/v3-ActCode",
    "code": "IMP",
    "display": "inpatient encounter"
  },
  "type": [
    {
      "coding": [
        {
          "system": "http://snomed.info/sct",
          "code": "305351004",
          "display": "Admission to intensive care unit"
        }
      ]
    }
  ],
  "subject": {
    "reference": "Patient/rajesh-kumar-icu"
  },
  "period": {
    "start": "2025-10-26T08:00:00+05:30"
  },
  "serviceProvider": {
    "reference": "Organization/aiims-delhi-icu"
  }
}
```

### 5. Result

The implementation of the `ShockModesFeatureSetObservation` FHIR Profile provides critical outcomes for predictive healthcare and AI integration.

#### Enables Predictive AI Exchange

*   The FHIR structure facilitates the high-frequency input required by the ShockModes model by standardizing the format of derived time-series features (such as Respiratory Rate Time Series Entropy extracted using `tsfresh`).
*   This standardization enables the model to achieve **83% sensitivity** and **94% specificity** for shock prediction 24 hours in advance.

#### Achieves Semantic Interoperability for Features

*   The use of precise, custom codes in `Observation.code` ensures that the receiving AI service understands the exact meaning of numerical values (e.g., differentiating raw HR from HR statistical autocorrelation coefficients).
*   This semantic clarity moves beyond basic syntactic exchange, enabling true interoperability between clinical systems and AI services.

#### Improves Clinical Workflow and Patient Safety

*   By exchanging pre-computed features rather than massive raw data logs, data transmission is optimized while still enabling timely predictions.
*   For patients like Rajesh Kumar, this approach allows the warning system to generate alerts 24 hours before shock onset.
*   This potentially reduces the 30–40% mortality rates associated with circulatory shock.

#### Establishes Data Provenance and Clinical Trust

*   Mandating the `derivedFrom` element ensures that predictive features can be traced back to their raw source data.
*   This process supports clinical validation and the FAIR principles of data reusability.
*   Transparency is essential for gaining clinician trust in AI-driven early warning systems and supporting quality assurance for clinical algorithms.

#### Supports Multimodal AI Integration

*   The profile accommodates the complex feature engineering requirements of modern predictive models like ShockModes.
*   ShockModes combines **3,117 statistical features** from vital signs with clinical intervention data.
*   This comprehensive approach enables more accurate predictions than single-parameter systems like simple shock index monitoring.

### 6. References

The sources include the following references:

1.  HL7 FHIR:
    a. `https://www.hl7.org/fhir/`
2.  Observation Resource:
    a. `https://www.hl7.org/fhir/observation.html`
3.  MedicationAdministration Resource:
    a. `https://www.hl7.org/fhir/medicationadministration.html`
4.  Procedure Resource:
    a. `https://build.fhir.org/procedure.html`
5.  SNOMED CT:
    a. `https://browser.ihtsdotools.org/`
6.  ShockModes Research Paper:
    a. `https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4396474`
7.  tsfresh Documentation:
    a. `https://tsfresh.readthedocs.io/`

## Computing for Medicine Lecture 10: Storyboarding, HL7 & FHIR

### Step 1: Define the Purpose, Gather the Requirements and Storyboard the Experience

#### Storyboarding Saves Lives!

The use of storyboarding and defining requirements led to measurable improvements in **PROJECT ESTHER**.

*   Hospital admissions fell **22 %** (from 9300 in 1998 to 7300 in 2003).
*   Hospital days for heart failure patients fell **28%** (from 3500 in 1998 to 2500 in 2000).
*   Waiting times for referral appointments with neurologists fell **84 %** (from 85 days in 2000 to 14 days in 2003).
*   Waiting times for referral appointments with gastroenterologists fell **71 %** (from 48 days in 2000 to 14 days in 2003).

### Step 2: Create a Conceptual Model

#### What is a Model and a Meta-Model?

A model is a description of what the modeler thinks to be relevant of a system.

A model includes the following elements:
*   Modeling syntax and semantics (i.e., the modeling language).
*   The representation of the concepts (how the concepts are represented in a concrete model, e.g., in a graphical way).
*   The modeling rules (e.g., the modeling steps), i.e., the guideline for applying the language.

##### Types of Meta- Models
*   **Functional:** These describe the functioning of the hospital.
*   **Technical:** This describes the information processing.
*   **Organizational:** This describes the organizational structure of the health information system.
*   **Data:** This describes the structure of data stored in a Health Information System (HIS).
*   **Business processes:** This describes the chronological and logical flow.

#### System, Use cases, Actors, Scenarios

*   **Use case:** This is a specific way of using the System. Non-technical persons should be able to understand it.
*   **Actor:** This is a Person, computer or device that interacts with the system.
*   **Scenario:** This is a particular instance of the use case.

#### Modeling Components and Diagrams

The following components and models are often involved:
*   Functional Components.
*   Technical Components.
*   Technical Model.
*   Organizational Model.
*   Organizational Components.
*   Data Model.
*   Business Process Model.
*   Other approaches from storyboarding.

Models and Diagrams used include:
*   Data Model: UML Diagram.
*   Activity Diagram, Sequence Diagrams, Statecharts.
*   Activity Diagram Statecharts.
*   Sequence Diagram.

### Step 3: Choose a Technical Framework, e.g. FHIR

#### Technical Interoperability: The Technology Layer

This is the technology layer.
*   It moves data from system A to system B, neutralizing the effects of distance.
*   It is domain independent.
*   It does not know or care about the meaning of what is exchanged.
*   **Information theory** is the foundation stone of technical interoperability.

#### Health Level 7 International (HL7)

*   HL7 is a Standards Development Organization.
*   It is now the **lingua franca** to pass health messages across systems.
*   At least two translations are required during information interchange.

The flow of information interchange is as follows:
$$\text{Internal format (computer)} \longrightarrow \text{Wire Format (connection)} \longrightarrow \text{Internal Format (computer)}$$

#### Sequential Steps in Object Oriented Software Development

Information interchange requires the following sequential steps:
1.  **Computational-Independent Model (CIM)**.
2.  **Platform-Independent Model (PIM)** - this is the conceptual design of a system.
3.  **Platform-Specific Model (PSM)** - this is the implementable design.
4.  **Code** - this is the actual software code, also referred to as wire-format.

#### HL7 Standard and Messages

The HL7 Standard is an example of Syntactic Interoperability. This standard includes Segment Definitions, Segments, and Reports. The system also uses HL7 Messages.

#### Core Idea: REST (Representational State Transfer)

REST forms the core idea for how standards like FHIR are structured.
*   RESTful APIs are used.
*   The architecture is built to copy the web.
*   It is organized around the concept of **"Resources"**.
*   All resources have references to other resources, extensions, and a human readable XHTML display.
*   Augmentation by Messages and Document paradigm is also possible.
*   FHIR features include: Open license, a focus on implementation, and a formal maturity process linked to Standard REST APIs.

The standard includes FHIR APIs.

### FHIR Scope, Modeling, and Resources

#### FHIR Scope of Models: General to Specific

The scope moves from General Message Definitions to Implementable Message Specifications.

The hierarchy of models includes:
1.  **A single domain-wide model (reference model)**, e.g., HL7 v3/RIM, ISO 13606, FHIR Resource definitions.
2.  **Technology-independent specifications constraining the domain wide model**, e.g., HL7 v3/RMIMs, CDA Templates, FHIR Profiles and archetypes.
3.  **Implementable message specifications**, which are mappings from technology-independent message specifications into the selected syntax, such as XML or JSON.

#### Reference Information Model (RIM): General Scope

The HL7 v3/RIM is the core, abstract model used by HL7 v3.

*   It provides a standardized, conceptual framework to represent healthcare data across different systems and domains.
*   It defines the building blocks (like classes, attributes, and relationships) that are used to create healthcare-related messages, documents, and interactions.
*   The RIM is highly abstract and is **not directly implementable**.
*   It serves as the foundation upon which more specific models and standards are built.
*   Its purpose is to ensure consistency and a unified approach to handling healthcare information.

##### Tying the RIM to the Storyboarding

The RIM contains abstract concepts. Considering the example of a patient encounter, the concepts include:

*   **Entity:** A person (e.g., the patient or the healthcare provider).
*   **Role:** The function of the entity in a particular context (e.g., "Patient" or "Doctor").
*   **Act:** An action or event that happens (e.g., "Encounter", "Observation").
*   **Participation:** The relationship between a role and an act (e.g., a patient participating in a doctor visit).

##### List out the objects at RIM level (Abstract Example)

*   **Entity** (Person)
    *   Role: Patient
    *   Role: Healthcare Provider (Doctor)
*   **Act** (Encounter)
    *   Participation: Patient (participates in Encounter)
    *   Participation: Doctor (participates in Encounter)

##### Python code stub for RIM (Abstract Classes)

```python
## HL7 v3 RIM Abstract Classes
class Entity:
    def __init__(self, name):
        self.name = name
class Role:
    def __init__(self, entity, role_type):
        self.entity = entity
        self.role_type = role_type
class Act:
    def __init__(self, act_type):
        self.act_type = act_type
        self.participations = []
```

#### Refined Message Information Model (RMIM): Specific

The RMIM is a specialization or refinement of the RIM.

*   It tailors the abstract concepts in the RIM to a particular use case or domain, such as lab results, patient records, or clinical encounters.
*   RMIMs are **more specific** and closer to implementation.
*   They define how data should be structured and exchanged in a given context based on the general principles of the RIM.
*   Each RMIM refines the abstract RIM by selecting and constraining the appropriate classes, attributes, and relationships for the specific message or data exchange scenario.

##### List out the details at RMIM level (Specific Example)

*   **EncounterMessage** (Message Header)
    *   Act: Encounter (type: Consultation)
        *   Participation: Patient (John Doe)
        *   Participation: Doctor (Dr. Smith)
        *   Observation: Blood Pressure (120/80 mmHg)

##### Python code stub for RMIM

```python
## RMIM
class EncounterMessage:
    def __init__(self, encounter_type):
        self.encounter = Act(encounter_type)
        self.observations = []

## RMIM (Method definition, likely within a class structure)
def add_participant(self, entity_name, role_type):
        entity = Entity(entity_name)
        role = Role(entity, role_type)
        participation = Participation(role, self.encounter)
        self.encounter.add_participation(participation)
```

### Deep Dive into FHIR

#### FHIR Resources and Conformance

*   Deep Dive into FHIR Resources.
*   Example of Conformance.
*   Example: Patient Resource.

#### Value Sets & Profiles

Value Sets are used to define allowable code values.

##### Example Value Set for Gender (JSON Format)

```json
{
    "resourceType": "ValueSet",
    "id": "example-gender",
    "status": "active",
    "description": "Example Value Set for Gender",
    "compose": {
        "include": [
            {
                "system": "http://hl7.org/fhir/administrative-gender",
                "concept": [
                    { "code": "male", "display": "Male" },
                    { "code": "female", "display": "Female" },
                    { "code": "other", "display": "Other" },
                    { "code": "unknown", "display": "Unknown" }
                ]
            }
        ]
    }
}
```

**Note the Difference from Profiles:** Profiles provide a set of constraints on a resource for particular contexts of use.

#### Implementation and Real-World Examples

*   FHIR Spec.
*   Hands On: Explore ClinFHIR & HAPI FHIR.
    *   HAPI FHIR documentation link: `https://hapifhir.io/hapi-fhir/docs/client/examples.html`.
    *   Google on FHIR: Open OHS End to End FHIR Solution.
*   Real World Implementations of FHIR Resources.
*   How UK is Building PHRs on FHIR.

##### India's FHIR Stack (ABDM)

India's implementation includes:
*   Discovery of Patient Information.
*   Linking to Hospital (HIP).
*   Health ID and Consent Management Framework.
*   Health ID.
*   Example Apps.
*   Profiling a FHIR Resource.
*   Example Query: "Suki, show me the medications of Mr. Sinha".

#### Steps for FHIR System Building

The implementation process involves:
*   Step 1: Building a FHIR Server.
*   Step 2: Adding a Patient.
*   Storing in a Database.

## Computing for Medicine Lecture 11: HL7 & FHIR Notes

### Technical Framework and Interoperability

#### Step 3: Choose a Technical Framework, e.g. FHIR

The selection of a technical framework, such as FHIR, is a necessary step. This choice is related to what is wanted and what the backend of the system looks like.

#### Technical Interoperability: The Technology Layer

This layer is known as the **technology layer**.

Characteristics of the Technology Layer:
*   **Moves data** from system A to system B, neutralizing the effects of distance.
*   It is **domain independent**.
*   It **does not know or care** about the meaning of what is exchanged.
*   **Information theory** is the foundation stone of technical interoperability.

#### Data Flow and Software Development Steps

The typical information interchange flow is described sequentially:

`Internal format ---> Wire Format ---> Internal Format (computer) (connection) (computer)`

Object Oriented Software Development requires the following sequential steps:

1.  **Computational-Independent Model (CIM)**.
2.  **Platform-Independent Model (PIM)** - the conceptual design of a system.
3.  **Platform-Specific Model (PSM)** - the implementable design.
4.  **Code**, the actual software code, also referred to as **wire-format**.

### Health Level 7 International (HL7)

HL7 is a **Standards Development Organization**.

*   HL7 is now the **lingua franca** to pass health messages across systems.
*   Information interchange requires at least **two translations**.

#### Syntactic Interoperability: HL7 Standard

The HL7 Standard is an example of Syntactic Interoperability. It consists of:

*   Segment Definitions.
*   Segments.
*   Reports.

### FHIR Standard and REST

#### HL7 Messages

The sources address the creation of HL7 Messages.

#### Core Idea: REST (Representational State Transfer)

*   **RESTful APIs** are built to copy the web.
*   They are organized around the concept of **"Resources"**.
*   All resources have references to other resources, extensions, and a **human readable XHTML display**.
*   Augmentation by **Messages and Document paradigm** is also possible.

The standard is linked to Standard REST APIs and FHIR APIs. These APIs feature:
*   An **open license**.
*   A focus on **implementation**.
*   A formal **maturity process**.

#### Deep Dive into FHIR Resources

### FHIR Scope of Models: General to Specific

The scope moves from General Message Definitions to Implementable Message Specifications. This involves three main components:

1.  **A single domain-wide model (reference model)**, e.g. HL7 v3/RIM, ISO 13606, FHIR Resource definitions.
2.  **Technology-independent specifications constraining the domain wide model**, e.g. HL7 v3/RMIMs, CDA Templates, FHIR Profiles and archetypes.
3.  **Implementable message specifications**, which are mappings from technology-independent message specifications into the selected syntax, such as XML or JSON.

### Reference Information Model (RIM)

The RIM is the core, abstract model used by HL7 v3. It provides a **standardized, conceptual framework** to represent healthcare data across different systems and domains.

#### RIM Details

*   The RIM defines the **building blocks** (like classes, attributes, and relationships) that are used to create healthcare-related messages, documents, and interactions.
*   It is **highly abstract** and **not directly implementable**.
*   Its purpose is to **ensure consistency and a unified approach** to handling healthcare information.
*   It serves as the **foundation** upon which more specific models and standards are built.

#### Tying the RIM to Storyboarding

The RIM contains abstract concepts. Considering the example of a patient encounter, the abstract concepts are:

*   **Entity**: A person (e.g., the patient or the healthcare provider).
*   **Role**: The function of the entity in a particular context (e.g., "Patient" or "Doctor").
*   **Act**: An action or event that happens (e.g., "Encounter", "Observation").
*   **Participation**: The relationship between a role and an act (e.g., a patient participating in a doctor visit).

##### Objects at RIM Level

The abstract objects at the RIM level are:

*   **Entity** (Person)
    *   Role: Patient
    *   Role: Healthcare Provider (Doctor)
*   **Act** (Encounter)
    *   Participation: Patient (participates in Encounter)
    *   Participation: Doctor (participates in Encounter)

### Refined Message Information Model (RMIM)

The RMIM is a **specialization or refinement of the RIM**.

*   RMIM tailors the abstract concepts in the RIM to a particular use case or domain, such as lab results, patient records, or clinical encounters.
*   RMIMs are **more specific** and **closer to implementation**.
*   They define how data should be structured and exchanged in a given context based on the general principles of the RIM.
*   Each RMIM refines the abstract RIM by selecting and constraining the appropriate classes, attributes, and relationships for the specific message or data exchange scenario.

##### Details at RMIM Level (Example)

In the patient encounter example, the details at the RMIM level are:

*   **EncounterMessage** (Message Header)
    *   **Act**: Encounter (type: Consultation)
        *   **Participation**: Patient (John Doe)
        *   **Participation**: Doctor (Dr. Smith)
        *   **Observation**: Blood Pressure (120/80 mmHg)

#### Python Code Stub for RIM and RMIM

##### HL7 v3 RIM Abstract Classes

```python
## HL7 v3 RIM Abstract Classes
class Entity:
    def __init__(self, name):
        self.name = name
class Role:
    def __init__(self, entity, role_type):
        self.entity = entity
        self.role_type = role_type
class Act:
    def __init__(self, act_type):
        self.act_type = act_type
        self.participations = []
```

##### RMIM Classes and Functions

```python
class EncounterMessage:
    def __init__(self, encounter_type):
        self.encounter = Act(encounter_type)
        self.observations = []

def add_participant(self, entity_name, role_type):
        entity = Entity(entity_name)
        role = Role(entity, role_type)
        participation = Participation(role, self.encounter)
        self.encounter.add_participation(participation)
```

### FHIR Conformance and Resources

#### Conformance, Value Sets & Profiles

##### Value Set Example

A Value Set specifies a defined group of codes used in a particular context.

```json
{   "resourceType": "ValueSet",   "id": "example-gender",   "status": "active",   "description": "Example Value Set for Gender",   "compose": {     "include": [       {         "system": "http://hl7.org/fhir/administrative-gender",         "concept": [           { "code": "male", "display": "Male" },           { "code": "female", "display": "Female" },           { "code": "other", "display": "Other" },           { "code": "unknown", "display": "Unknown" }         ]       }     ]   } }
```

##### Profiles

**Profiles** provide a set of **constraints on a resource for particular contexts of use**. Note the difference from Value Sets.

*   FHIR Spec.
*   Profiling a FHIR Resource.
*   It is suggested to follow the page link for understanding resources.

#### Example: Patient Resource

The following table summarizes the purpose and key elements of sections within the Patient Resource:

| Section Purpose | Key Elements |
| :--- | :--- |
| **Resource Identity & Metadata:** Tracks and manages the version and identity of this patient resource. | `id, meta.lastUpdated` |
| **Human Readable Summary:** Ensures clinicians can read an intelligible summary of the patient’s data. | `text, div, p` |
| **Extension:** Adds non-core data while keeping the structure valid. | `extension, url, valueCode` |
| **Identifier:** Holds formal IDs such as MRN. | `identifier, system, value` |
| **Standard Demographics:** Core patient attributes and provider linkage. | `name, gender, birthDate, careProvider` |

An Example JSON for the Patient Resource exists.

#### Openly Available FHIR Servers and Hands On

*   **Openly Available FHIR Servers**: HAPI FHIR.
*   HAPI FHIR documentation link: `https://hapifhir.io/hapi-fhir/docs/client/examples.html`.
*   Hands On: Explore ClinFHIR & HAPI FHIR.

### Real-World Implementations

FHIR resources have real world implementations.

#### India on FHIR (ABDM)

India utilizes the FHIR Stack (ABDM). Key components include:

*   Discovery of Patient Information.
*   Linking to Hospital (HIP).
*   Health ID and Consent Management Framework.
*   Health ID.
*   Example Apps.
*   Query Example: `Suki, show me the medications of Mr. Sinha`.

#### Other Implementations

*   Google on FHIR: Open OHS End to End FHIR Solution.
*   How UK is Building PHRs (Personal Health Records) on FHIR.

#### General Implementation Steps

1.  **Step 1:** Building a FHIR Server.
2.  **Step 2:** Adding a Patient.
3.  **Storing in a Database**.

## Computing for Medicine Lecture 12: FHIR and Analytics

### 1. FHIR Resource Example: Patient Resource

#### Summary of the Patient Resource

The Patient Resource structure includes several key elements necessary for tracking patient data:

| Section Purpose | Key Elements | Detail |
| :--- | :--- | :--- |
| **Resource Identity & Metadata** | `id`, `meta.lastUpdated` | Tracks and manages the version and identity of this patient resource. |
| **Human Readable Summary** | `text`, `div`, `p` | Ensures clinicians can read an intelligible summary of the patient’s data. |
| **Extension** | `extension`, `url`, `valueCode` | Adds non-core data while keeping the structure valid. |
| **Identifier** | `identifier`, `system`, `value` | Holds formal IDs such as MRN. |
| **Standard Demographics** | `name`, `gender`, `birthDate`, `careProvider` | Core patient attributes and provider linkage. |

#### Example JSON for the Patient Resource

This section provides the context for Example JSON for the Patient Resource.

### 2. FHIR Scope of Models: General to Specific

The scope of models ranges from General Message Definitions to Implementable Message Specifications. This progression involves three main levels of specification:

*   **A single domain-wide model (reference model)**, e.g., HL7 v3/RIM, ISO 13606, FHIR Resource definitions.
*   **Technology-independent specifications constraining the domain wide model**, e.g., HL7 v3/RMIMs, CDA Templates, FHIR Profiles and archetypes.
*   **Implementable message specifications**, mappings from technology-independent message specifications into the selected syntax, such as XML or JSON.

### 3. Reference Information Model (RIM)

#### Reference Information Model: General Scope

The **HL7 v3/RIM (Reference Information Model)** is the core, abstract model used by HL7 v3.

*   It provides a standardized, conceptual framework to represent healthcare data across different systems and domains.
*   It defines the building blocks (like classes, attributes, and relationships) that are used to create healthcare-related messages, documents, and interactions.
*   The RIM is **highly abstract** and is **not directly implementable**.
*   It serves as the foundation upon which more specific models and standards are built.
*   Its purpose is to ensure consistency and a unified approach to handling healthcare information.

### 4. Tying the RIM to Storyboarding

The RIM contains abstract concepts. Considering an example of a patient encounter helps illustrate these abstract concepts:

*   **Entity:** A person (e.g., the patient or the healthcare provider).
*   **Role:** The function of the entity in a particular context (e.g., "Patient" or "Doctor").
*   **Act:** An action or event that happens (e.g., "Encounter", "Observation").
*   **Participation:** The relationship between a role and an act (e.g., a patient participating in a doctor visit).

#### List out the objects at RIM level

The objects listed at the RIM level are:

*   **Entity (Person)**
    *   Role: Patient
    *   Role: Healthcare Provider (Doctor)
*   **Act (Encounter)**
    *   Participation: Patient (participates in Encounter)
    *   Participation: Doctor (participates in Encounter)

#### Python code stub for RIM

This code illustrates the HL7 v3 RIM Abstract Classes:

```python
## HL7 v3 RIM Abstract Classes
class Entity:
    def __init__(self, name):
        self.name = name
class Role:
    def __init__(self, entity, role_type):
        self.entity = entity
        self.role_type = role_type
class Act:
    def __init__(self, act_type):
        self.act_type = act_type
        self.participations = []
```

### 5. Refined Message Information Model (RMIM)

#### Refined Message Information Model: Specific

The **RMIM** is a specialization or refinement of the RIM.

*   It tailors the abstract concepts in the RIM to a particular use case or domain, such as lab results, patient records, or clinical encounters.
*   RMIMs are **more specific** and **closer to implementation**.
*   They define how data should be structured and exchanged in a given context based on the general principles of the RIM.
*   Each RMIM refines the abstract RIM by selecting and constraining the appropriate classes, attributes, and relationships for the specific message or data exchange scenario.

#### List out the details at RMIM level

The details listed at the RMIM level, using the encounter example, are:

*   **EncounterMessage (Message Header)**
    *   Act: Encounter (type: Consultation)
        *   Participation: Patient (John Doe)
        *   Participation: Doctor (Dr. Smith)
        *   Observation: Blood Pressure (120/80 mmHg)

#### RMIM Python Code

This code stub demonstrates the RMIM structure, including the `EncounterMessage` class and the `add_participant` method:

```python
## RMIM
class EncounterMessage:
    def __init__(self, encounter_type):
        self.encounter = Act(encounter_type)
        self.observations = []

def add_participant(self, entity_name, role_type):
        entity = Entity(entity_name)
        role = Role(entity, role_type)
        participation = Participation(role, self.encounter)
        self.encounter.add_participation(participation)
```

### 6. FHIR Implementation and Analytics

#### Openly Available FHIR Servers

One example of an Openly Available FHIR Server is **HAPI FHIR**. Documentation and examples can be explored at: `https://hapifhir.io/hapi-fhir/docs/client/examples.html`.

#### Hands On

The activity suggested is to Explore ClinFHIR & HAPI FHIR.

#### Real World Implementations of FHIR Resources

##### India's FHIR Stack (ABDM)

India’s FHIR Stack (ABDM) covers several key components:

*   Discovery of Patient Information.
*   Linking to Hospital (HIP).
*   Health ID and Consent Management Framework.
*   Example Apps, such as Health ID.
*   An example query demonstration used is: "Suki, show me the medications of Mr. Sinha".

##### Google on FHIR

Google provides the Open OHS End to End FHIR Solution.

##### UK Implementation

The UK is Building PHRs (Personal Health Records) on FHIR. This process involves:

*   Step 1: Building a FHIR Server.
*   Step 2: Adding a Patient.
*   Storing in a Database.

##### UCSF Use of AWS APIs for FHIR

UCSF uses AWS APIs for FHIR. This supports various functions:

*   Conditional creation, deletion, update of resources, and recovery of deleted files.
*   Secure processing of clinical data in compliance with HIPAA.
*   Data analytics based on artificial intelligence.
*   Bulk access to FHIR-enabled servers with role-based access control privileges.

##### FHIR Capabilities

*   FHIR allows integration of **Determinants of Health**.
*   FHIR and **Agentic AI** are also related topics.

### 7. SMART on FHIR

#### Definition and Function

**SMART on FHIR** stands for **S**ubstitutable **M**edical **A**pplications, **R**eusable **T**echnologies on **F**ast **H**ealthcare **I**nteroperability **R**esources.

*   It is a framework that allows third-party apps to connect securely to electronic health record (EHR) systems—like Epic, Cerner, or Allscripts—in a standardized, interoperable way.
*   Essentially, it is the **“app store for healthcare data”**.

Together, SMART and FHIR define key behaviors:

*   SMART defines how apps launch and authenticate within an EHR.
*   FHIR defines how data are structured and exchanged.
*   This collaboration makes it possible for apps to access patient data in a standardized format, securely and consistently across different health systems.

#### What SMART Does

SMART provides essential security and launch functionalities:

*   It adds an **authorization and app-launch layer** on top of FHIR.
*   It defines how apps are installed, authenticated, and granted permissions to read or write data.
*   It uses **OAuth 2.0** and **OpenID Connect** for secure user login and token-based data access.

#### Applications and Regulatory Use

*   **Apple Health** uses SMART on FHIR to pull health data from hospitals.
*   EHR vendor platforms that rely on SMART on FHIR include **Epic App Orchard**, **Cerner CODE**, and **Allscripts Developer Program**.
*   The **CMS Interoperability and Prior Authorization Rule (CMS-0057-F)** (effective 2026–2027) also builds upon FHIR APIs for payer–provider data exchange.

### 8. Prior Authorization Reform in US CMS (MEDICAID)

The US CMS is implementing Prior Authorization Reform.

*   Starting in 2026, affected payers will be required to issue prior authorization decisions within **72 hours for urgent requests** and **seven calendar days for non-urgent requests**.
*   This reform aims to accelerate patient care.