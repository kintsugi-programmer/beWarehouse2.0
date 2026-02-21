# NS

Syllabus for the Mid-Sem Examination

(1) The first three chapters from the Network Science Book including the end-of-the-chapter exercises:
https://networksciencebook.com
- Introduction
- Graph Theory
- Random Graphs

(2) Research articles given as 'Reading Material':
- 01_Scale Free Networks and How they impact everything by Albert-Laszlo Barabasi and Eric Bonabeau SCIAM
- 02_Small-World-Watts-Strogatz-Nature-1998
- 03_Airport_Network_of_India_PhysicaA-2005
- 04_Nature-ErrorAttack_Tolerance
- 05_Centrality_Lethality_in_Protein_Interaction_Networks
- 06_Indian_Railways_Network_PRE
- 07_Flavor_Network_Ahn_SciRep_2011

(3) Content covered in Assignment-01

STRUCTURE
- MCQs with nagative marking
- MCQs without nagative marking
- Short Answer Type Questions

## NS 1st Half

![alt text](image.png)

### 1. Introduction to Network Science

#### 1.1. Complex Systems
*   **Definition:** A system comprising a large number of sophisticated functional elements, intricately connected with each other to perform specific tasks, which otherwise cannot be executed by subsets of the system.
*   **Core Concept:** "Sum of parts is not the same as the whole."
*   **Complexity:**
    1.  Composed of many interconnected parts; compound; composite (e.g., a complex highway system).
    2.  Characterized by a very complicated or involved arrangement of parts, units, etc. (e.g., complex machinery).
    3.  So complicated or intricate as to be hard to understand or deal with (e.g., a complex problem).

#### 1.2. The Role of Networks
*   Behind each system studied in complexity, there is an intricate wiring diagram, or a network, that defines the interactions between the components.
*   **Fundamental Rule:** We will never understand complex systems unless we map out and understand the networks behind them.

#### 1.3. Real-World Case Studies

##### A. The Capture of Saddam Hussein
*   **Context:** The capture was not based on fresh intelligence but on pre-invasion social links found in old family album photos.
*   **Network Strategy:** The hierarchical tree capturing the official organization of the Iraqi government was useless. The focus shifted to the social network.
*   **Key Lessons:**
    *   Shows the strong predictive power of networks.
    *   Underlines the need for accurate maps of networks.
    *   Demonstrates the remarkable stability of these networks.
    *   Shows that the *choice* of network matters (Social vs. Hierarchical).

##### B. The August 15, 2003 Blackout
*   **Event:** Massive power outage in the US Northeast (Toronto, Detroit, Cleveland, Columbus, Long Island).
*   **Mechanism:** Vulnerability due to interconnectivity.
*   **Lessons:**
    *   Network structure affects the robustness of a complex system.
    *   Failures follow reproducible laws that can be quantified and predicted.
    *   Need to assess the interplay between network structure and dynamical processes (e.g., flow of electricity).

#### 1.4. Characteristics of Network Science
1.  **Interdisciplinary:** Emerging in various domains (science, nature, technology).
2.  **Quantitative and Mathematical:** Uses graph theory and statistical mechanics.
3.  **Computational:** relies on large-scale data processing.
4.  **Empirical:** Data-driven (e.g., mapping the internet, social graphs).

#### 1.5. Impact of Network Science

##### Economic Impact
*   **Tech Giants:** Google, Cisco, Facebook, Twitter.
*   **Marketing:** Viral marketing, reducing employee churn, optimizing knowledge diffusion.
*   **Organizational Mapping:**
    *   Case study of a Hungarian company: Management believed information flowed hierarchically.
    *   Reality: A "Safety Expert" (ordinary employee) was the hidden hub.
    *   Network analysis reveals actual influence versus official hierarchy.

##### Health and Biology
*   **Drug Design:**
    *   Reducing inflammation/fever/pain (Aspirin) vs. preventing heart attacks.
    *   Understanding side effects (bleeding, ulcers).
    *   Network Pharmacology/Medicine: Designing drugs based on the wiring diagram of the cell.
*   **Human Disease Network (Diseaseome):**
    *   Bipartite network connecting diseases to genes.
    *   Shows that diseases are not independent but connected via shared genetic mutations.
*   **Brain Research:**
    *   Human Connectome Project (HCP): Mapping complete structural and functional neural connections.
    *   Brain contains 10-100 billion neurons.

##### Military and Security
*   **Netwar:** Fighting terrorism and military engagements.
*   **Structure:** Network models used for decision-making and operational coordination (e.g., factoring in population beliefs, narcotics trade, and insurgent support).

---

### 2. Graph Theory Fundamentals

#### 2.1. Origins: The Bridges of Königsberg (1735)
*   **Problem:** Can one walk across the seven bridges and never cross the same one twice?
*   **Euler’s Theorem:**
    *   (a) If a graph has more than two nodes of odd degree, there is no path.
    *   (b) If a graph is connected and has no nodes of odd degree, it has an Euler circuit (start and end at same point).
    *   (c) If a graph has exactly two nodes of odd degree, it has an Euler path (start and end at different points).
*   **Significance:** Foundation of Graph Theory.

#### 2.2. Components of a Complex System
*   **Components:** Nodes, vertices ($N$).
*   **Interactions:** Links, edges ($L$).
*   **System:** Network, graph ($N, L$).

#### 2.3. Network Representations

##### Adjacency Matrix ($A$)
*   A square matrix of size $N \times N$.
*   **Elements ($A_{ij}$):**
    *   $A_{ij} = 1$ if there is a link pointing from node $j$ to node $i$.
    *   $A_{ij} = 0$ if there is no link.
*   **Characteristics:**
    *   **Undirected Graph:** Matrix is symmetric ($A_{ij} = A_{ji}$).
    *   **Directed Graph:** Matrix is not necessarily symmetric ($A_{ij} \neq A_{ji}$).
    *   **Sparse Networks:** Most real networks are sparse ($L \ll L_{max}$), meaning the matrix is mostly zeros.

##### Edge List
*   A list of pairs $(i, j)$ representing links.
*   More memory efficient for sparse networks.

#### 2.4. Basic Metrics

##### Node Degree ($k$)
*   **Definition:** The number of links connected to a node.
*   **Undirected Network:**
    *   $k_i = \sum_{j=1}^{N} A_{ij}$
    *   Total Links: $L = \frac{1}{2} \sum_{i=1}^{N} k_i$
    *   Average Degree: $\langle k \rangle = \frac{2L}{N}$
*   **Directed Network:**
    *   **Incoming Degree ($k_{in}$):** Links pointing to the node. $k_i^{in} = \sum_{j=1}^{N} A_{ij}$
    *   **Outgoing Degree ($k_{out}$):** Links starting from the node. $k_j^{out} = \sum_{i=1}^{N} A_{ij}$
    *   Total Links: $L = \sum k_{in} = \sum k_{out}$
    *   Average Degree: $\langle k \rangle = \frac{L}{N}$

##### Complete Graph
*   **Definition:** Every node is connected to every other node.
*   **Maximum Links ($L_{max}$):**
    *   $L_{max} = \frac{N(N-1)}{2}$
*   **Average Degree:** $\langle k \rangle = N - 1$.

##### Weighted Networks
*   Links have a defined weight ($w_{ij}$), strength, or flow parameter.
*   $A_{ij} = w_{ij}$ if a link exists.

##### Bipartite Networks
*   **Definition:** A network with two distinct sets of nodes ($U$ and $V$). Links only connect nodes from set $U$ to set $V$ (no $U-U$ or $V-V$ connections).
*   **Projections:**
    *   **Projection U:** Nodes from set $U$ are connected if they link to the same node in set $V$.
    *   **Projection V:** Nodes from set $V$ are connected if they link to the same node in set $U$.
*   **Examples:**
    *   **Hollywood:** Actors (U) and Movies (V).
    *   **Science:** Authors (U) and Papers (V).
    *   **Diseaseome:** Diseases (U) and Genes (V).
    *   **Flavor Network:** Ingredients (U) and Compounds (V).

#### 2.5. Paths and Distances

##### Path
*   A sequence of nodes such that each node is connected to the next.
*   **Path Length:** Number of links in the path.

##### Shortest Path (Geodesic Path, $d$)
*   The path with the fewest links between two nodes.
*   **Distance ($d_{ij}$):** Length of the shortest path between $i$ and $j$.
*   **Average Path Length ($\langle d \rangle$):** Average over all shortest paths between all pairs of nodes. Offers a measure of a network's overall navigability.
    *   $\langle d \rangle \approx \frac{\ln N}{\ln \langle k \rangle}$ (for random networks).

##### Diameter ($d_{max}$)
*   The longest shortest path in the network.

##### Breadth-First Search (BFS) Algorithm
Used to find distances and connected components.
1.  Start at node $i$ (distance 0).
2.  Find adjacent nodes, mark as distance 1, put in queue.
3.  Take first node from queue, find unmarked neighbors, mark as distance $n+1$, put in queue.
4.  Repeat until target node found or queue empty.

#### 2.6. Clustering Coefficient ($C$)
*   **Definition:** Measures the degree to which neighbors of a node link to each other (triangles).
*   **Local Clustering Coefficient ($C_i$):**
    $$C_i = \frac{2L_i}{k_i(k_i - 1)}$$
    *   $L_i$: Number of links between the $k_i$ neighbors of node $i$.
    *   $k_i(k_i - 1)/2$: Maximum possible links between neighbors.
    *   $C_i \in$.
*   **Average Clustering Coefficient ($\langle C \rangle$):**
    $$\langle C \rangle = \frac{1}{N} \sum_{i=1}^{N} C_i$$
*   **Global Interpretation:** Probability that two neighbors of a randomly selected node are connected.

---

### 3. Random Networks (The Erdős-Rényi Model)

#### 3.1. The $G(N, p)$ Model
*   **Definition:** A network of $N$ nodes where each pair of nodes is connected with probability $p$.
*   **Parameters:**
    *   $N$: Number of nodes.
    *   $p$: Probability of connection.
*   **Expected Number of Links:** $\langle L \rangle = p \frac{N(N-1)}{2}$.
*   **Average Degree:** $\langle k \rangle = p(N-1)$.

#### 3.2. Degree Distribution ($P_k$)
*   **Definition:** Probability that a node has exactly $k$ links.
*   **Binomial Distribution:**
    $$P_k = \binom{N-1}{k} p^k (1-p)^{N-1-k}$$
*   **Derivation steps:**
    1.  Probability of $k$ connections: $p^k$.
    2.  Probability of $N-1-k$ non-connections: $(1-p)^{N-1-k}$.
    3.  Combinatorial factor (ways to choose $k$ links): $\binom{N-1}{k}$.
*   **Poisson Approximation:** For large $N$ and small $p$ (where $\langle k \rangle$ is constant):
    $$P_k = e^{-\langle k \rangle} \frac{\langle k \rangle^k}{k!}$$
*   **Properties:**
    *   Peaked distribution ("Bell curve" shape).
    *   Nodes have degrees close to $\langle k \rangle$.
    *   **Hubs are forbidden:** It is extremely rare to find nodes with significantly more or fewer links than the average.

#### 3.3. Evolution of Random Networks (Phase Transitions)
As $\langle k \rangle$ (or $p$) increases, the network structure changes drastically.
1.  **Subcritical Regime ($\langle k \rangle < 1$):**
    *   Isolated clusters.
    *   Sizes of clusters are small (Tree-like).
    *   Largest cluster size $\sim \ln N$.
2.  **Critical Point ($\langle k \rangle = 1$):**
    *   Phase transition occurs.
    *   Great diversity in cluster sizes.
3.  **Supercritical Regime ($\langle k \rangle > 1$):**
    *   **Giant Component ($N_G$) emerges.**
    *   $N_G \sim (p - p_c)N$.
    *   Numerous isolated components coexist with the giant component.
4.  **Connected Regime ($\langle k \rangle > \ln N$):**
    *   The giant component absorbs all nodes.
    *   Network becomes fully connected ($N_G \simeq N$).

#### 3.4. Small World Property
*   **Six Degrees of Separation:**
    *   **1967 Milgram Experiment:** "Small World Problem." Letters sent to target in Boston via acquaintances. Average path length $\approx 6$.
    *   **1991 Play/Movie:** John Guare popularized the phrase "Six degrees of separation."
    *   **1998 Watts-Strogatz:** Defined small-world networks as having high clustering (like regular lattices) but short path lengths (like random graphs).
*   **Calculation for Random Graphs:**
    *   $N \approx \langle k \rangle^d$ (Number of nodes reachable at distance $d$).
    *   **Diameter:** $d \approx \frac{\ln N}{\ln \langle k \rangle}$.
    *   For the WWW ($N \approx 3 \times 10^5$, $\langle k \rangle \approx 4.6$), diameter $\approx 11$. (Actual observed: 19 degrees of separation).
*   **Significance:** Distances in random graphs are small, scaling logarithmically with $N$.

#### 3.5. Clustering in Random Networks
*   The probability that two neighbors of a node are connected is simply equal to the global probability $p$.
*   $C_{rand} = p = \frac{\langle k \rangle}{N}$.
*   **Observation:** For large $N$, $C_{rand}$ is very small (goes to 0). Real networks often have much higher $C$ than random networks.

---

### 4. Scale-Free Networks

#### 4.1. Introduction
*   **Observation:** Real networks (WWW, Internet, Metabolic, Citation) deviate from the Poisson degree distribution.
*   **Pattern:** They follow a **Power Law**.

#### 4.2. Power Law and Scale-Free Property
*   **Discrete Formalism:** $p_k$ is the probability a node has degree $k$.
*   **Continuum Formalism:**
    $$P(k) \sim k^{-\gamma}$$
    *   $\gamma$: Degree exponent.
*   **Why "Scale-Free"?**
    *   Power laws do not have a characteristic scale (or average) that typifies the system, unlike the "bell shape" of random networks.
    *   There is no "typical" node.
*   **Linearity:** On a Log-Log plot ($\log P(k)$ vs $\log k$), a power law appears as a straight line with slope $-\gamma$.

#### 4.3. Hubs
*   **Definition:** Nodes with a tremendous number of connections (high $k$).
*   **Role:**
    *   Hold the network together.
    *   Dominate the structure (Heavy tail distribution).
*   **Contrast:**
    *   **Random Network:** Deeply democratic; nodes have approx same links. Hubs effectively forbidden.
    *   **Scale-Free Network:** Dictatorial; dominated by a few hubs.
*   **80/20 Rule (Pareto Principle):** 20% of inputs cause 80% of outputs. (e.g., 20% of heavy users act as hubs).

#### 4.4. Universality
*   Many diverse systems share the scale-free topology ($2 < \gamma < 3$).
*   **Examples:**
    *   **Internet Backbone:** Nodes=Routers. $\gamma \approx 2.2$.
    *   **WWW:** Nodes=Webpages. $\gamma_{in} \approx 2.1$, $\gamma_{out} \approx 2.45$.
    *   **Citation Network:** Nodes=Papers. $\gamma \approx 3$.
    *   **Metabolic Networks:** Nodes=Metabolites. $\gamma \approx 2.2$.
    *   **Protein Interaction:** $\gamma \approx 2.4$.
    *   **Phone Calls:** $\gamma = 8.4$ (High exponent, borders on random).

#### 4.5. Robustness
*   **Question:** How does network structure affect stability against errors and attacks?
*   **Random Failures:**
    *   **Scenario:** Random removal of nodes.
    *   **Scale-Free Response:** **Robust.** Since most nodes have few links, probability of removing a hub is negligible. The network stays connected (Diameter doesn't increase significantly).
*   **Targeted Attacks:**
    *   **Scenario:** Deliberate removal of the highest-degree nodes (hubs).
    *   **Scale-Free Response:** **Vulnerable.** Removing a few hubs breaks the network into isolated fragments rapidly.
    *   **Threshold:** Critical fraction $f_c$ of nodes removed leads to collapse.

#### 4.6. Ultra-Small Property
*   Distances in scale-free networks are smaller than in random networks.
*   **Formula:** $\langle l \rangle \sim \frac{\ln \ln N}{\ln (\gamma - 1)}$ (for $2 < \gamma < 3$).
*   **Physical meaning:** Hubs act as bridges, drastically shortening the path between any two nodes.

#### 4.7. Generating Scale-Free Networks
*   **Configuration Model:**
    1.  Generate a degree sequence $\{k_1, ..., k_N\}$ from a power-law distribution.
    2.  Create "stubs" (half-links) for each node.
    3.  Randomly pair stubs to form links.
*   **Structural Constraint:** For $\gamma < 2$, the mean degree diverges. Graphical degree sequences become rare as largest hub grows faster than $N$.

---

### 5. Specific Case Studies & Paper Excerpts

#### 5.1. Indian Railways Network (IRN)
*   **Source:** "06_Indian_Railways_Network_PRE.pdf"
*   **Structure:**
    *   Mean distance $D(N)$ scales as $A + B \log N$.
    *   $A \approx 1.33$, $B \approx 0.13$.
    *   Small-world behavior observed.
    *   Shortest path length distribution $P(l)$ peaks around minimal links.

#### 5.2. Flavor Network (Food Pairing)
*   **Source:** "07_Flavor_Network_Ahn_SciRep_2011.pdf"
*   **Type:** Bipartite Network (Ingredients $\leftrightarrow$ Flavor Compounds).
*   **Projected Network:** Flavor Network (Nodes = Ingredients).
    *   Link exists if ingredients share significant flavor compounds.
    *   **Observation:** Network is too dense ($<k> \approx 214$). Requires "backbone extraction" to see significant links.
    *   **Clusters:**
        *   Western cuisine: Tends to pair ingredients that *share* flavor compounds.
        *   East Asian cuisine: Tends to pair ingredients that *avoid* sharing compounds.
*   **Key Insight:** Reformulates food pairing principles using network science.

#### 5.3. Airport Network of India (ANI)
*   **Source:** "03_Airport_Network_of_India_PhysicaA-2005.pdf"
*   **Nodes:** 79 airports.
*   **Paths:** 6162 distinct routes.
*   **Statistics:**
    *   Connected by direct flight: ~7%.
    *   Reach by changing max 1 flight: ~68%.
    *   Reach by changing max 2 flights: ~99%.
*   **Conclusion:** High efficiency/convenience for travel.

#### 5.4. Protein Interaction Networks (Centrality-Lethality)
*   **Source:** "05_Centrality_Lethality...pdf"
*   **Hypothesis:** Highly connected proteins (hubs) are more essential for survival.
*   **Evidence:**
    *   Yeast (S. cerevisiae) network: Removal of red nodes (hubs) causes cell death.
    *   Removal of green/yellow nodes (low degree) causes slow growth or no effect.
    *   **Rule:** Centrality correlates with Lethality.

#### 5.5. Watts-Strogatz Model (Small-World Rewiring)
*   **Source:** "02_Small-World-Watts-Strogatz-Nature-1998.pdf"
*   **Algorithm:**
    1.  Start with a regular ring lattice ($N$ nodes, $k$ neighbors).
    2.  Randomly rewire edges with probability $p$.
*   **Results:**
    *   $p=0$: Regular Lattice (High Clustering, High Path Length).
    *   $p=1$: Random Graph (Low Clustering, Low Path Length).
    *   **Intermediate $p$ (Small World):** Retains High Clustering ($C(p) \sim C(0)$) but Path Length drops rapidly ($L(p) \approx L(random)$).
*   **Impact:** Disease spreading speeds up significantly with just a few percent of rewired links.

---

### 6. Mathematical Summary

| Measure | Random Network | Scale-Free Network |
| :--- | :--- | :--- |
| **Degree Distribution** | $P(k) \approx e^{-\langle k \rangle} \frac{\langle k \rangle^k}{k!}$ (Poisson) | $P(k) \sim k^{-\gamma}$ (Power Law) |
| **Path Length** | $\ln N$ | $\ln \ln N$ (Ultra-small) |
| **Clustering Coeff.** | $C \sim \langle k \rangle / N$ (Small) | Independent of $N$ (High) |
| **Hubs** | Forbidden | Dominant |
| **Robustness** | Vulnerable to random failure | Robust to random, Vulnerable to targeted |

#### Important Formulas
*   **Possible Links:** $N(N-1)/2$
*   **Density:** $L / L_{max}$
*   **Average Degree:** $\langle k \rangle = 2L/N$
*   **Clustering (Local):** $C_i = 2L_i / (k_i(k_i-1))$
*   **Power Law Normalization:** $\int_{k_{min}}^{\infty} P(k) dk = 1$

## NS MidSem

- **1. Core Concepts and Network Building Blocks**
  - **What is a Complex System?**
    - Imagine a massive machine made of many tiny, smart parts. A complex system consists of a **large number of sophisticated functional elements**.
    - These elements are intricately connected to perform specific tasks.
    - **The Golden Rule**: If you take a small group (a subset) of these elements out of the system, they **cannot** execute the tasks on their own. They rely on the entire network!
  - **Why did Network Science Emerge?**
    - The field of network science blew up because of two main forces:
      - **Availability of network maps**: We finally had the data and technology to map out massive networks.
      - **Universality of network characteristics**: Scientists discovered that different networks (like the internet, social groups, and biology) all share the same universal rules.
  - **Metcalfe's Law**
    - This law helps us measure how much a network is worth.
    - It states that the value of a network is **proportional to the square of the number of its nodes**. (For example, if a network has 10 users, its value is tied to 100!).
  - **Understanding Average Degree (`<k>`)**
    - The "degree" of a node is simply how many connections it has.
    - For an undirected and unweighted graph, the formula for the average degree of the whole network is: **`2L / N`**.
      - `L` stands for the total Number of edges (links).
      - `N` stands for the total Number of nodes.
  - **Complete Graphs vs. Sparse Networks**
    - **Complete Graph**: A network where every single node is connected directly to every other node.
      - The average degree (`<k>`) is **`N - 1`** (since each node connects to all other nodes).
      - The total number of edges (`L`) is **`N(N - 1) / 2`**.
    - **Sparse Network**: A network with very few connections compared to what is possible.
      - Rule 1: **`L << L_max`** (The actual links are much, much less than the maximum possible links).
      - Rule 2: **`<k> << N - 1`** (The average degree is much, much less than the maximum possible degree).
      - **Real-world fact**: Real-world graphs are known to be **Sparse and having a Scale-Free Degree Distribution**.
  - **Directed vs. Undirected Graphs**
    - **Undirected Graphs**: Connections go both ways automatically (like being friends). Examples include the Actor Network, Co-authorship Networks, and Protein interaction networks.
    - **Directed Graphs**: Connections have a strict direction (like a one-way street). Example: A **Phone call network** (because a call is initiated by one person to another). Therefore, a phone call network is **NOT** an undirected graph.
  - **What is a Sink Node?**
    - In a directed graph, a **sink** is a "dead end." It is a node where arrows only point *in*, and nothing points *out*.
    - Mathematically, it is a node with an out-degree of zero: **`k_out = 0`**.

- **2. Understanding Paths in a Network**
  - **Self-Avoiding Path**
    - This is a path that **does not intersect itself**. It simply goes from point A to point B without ever crossing its own tracks.
  - **Hamiltonian Path**
    - This is a path that **visits every node exactly once**. You have to stop at every single destination, but you cannot visit any destination twice!
  - **Eulerian Path**
    - This is a path that **traverses each link exactly once**. You have to travel down every single road, but you cannot use the same road twice.
    - *Historical Puzzle*: The famous "Konigsberg Bridge Problem" asked if an Eulerian path was possible in the city of Konigsberg. The answer was no, because the Konigsberg graph had **four nodes with an odd number of links**. (For an Eulerian path to work, you can only have 0 or exactly 2 nodes with an odd number of connections).

- **3. Specific Network Models and Mathematical Rules**
  - **Scale-Free Networks**
    - These are networks dominated by a few massive "hubs" (like major airports).
    - Mathematical limits: They have been shown to be absolutely **non-existent** if their degree exponent (`γ` or gamma) is **`γ < 2`**.
    - The standard deviation of a scale-free degree distribution is mathematically **Infinity**.
    - If you are tasked with plotting power laws for these networks, the advised strategy is to **Use a Log-Log Plot**.
  - **Random Networks (Erdős-Rényi / Gilbert Models)**
    - If you have a large network (large `N`) with very few average connections (small `<k>`), the degree distribution of the random graph will take the shape of a **Poisson Distribution**.
    - **The Critical Point**: A random network is said to have achieved the 'critical point' when its average degree is exactly one: **`<k> = 1`**.
    - *Example Calculation*: Imagine a real-world graph has 101 nodes and 2525 edges. If you build its random network counterpart using the Gilbert `G(N,p)` strategy, the probability (`p`) that any two nodes connect to each other is **`0.5`**.
  - **Watts and Strogatz Model**
    - This model explores the "small-world" phenomenon.
    - When implementing their strategy to randomize a "k-regular graph", the number of laps that one needs to take is **`k/2`**.
    - In their famous 1998 Nature paper, they investigated the C. elegans Neuronal Network, North America's Power Grid, and the Actors' Network.
    - They did **NOT** investigate the **Yeast Protein Interaction Network**.
  - **Finding Shortest Paths**
    - **Breadth First Search (BFS)**: An algorithm used for finding the shortest path between two nodes. Its computational complexity is **`O(N + L)`** (where N = Number of nodes, L = Number of edges).
    - **Adjacency Matrix Method**: While calculating the shortest paths starting from an adjacency matrix is highly elegant, it **is not preferred for large networks due to its inefficiency**.
  - **Error and Attack Tolerance**
    - To figure out how tough a complex network is against random errors or targeted attacks, scientists investigate two main measures:
      - **Size of the giant component**
      - **Average size of the fragmented clusters**.

- **4. Real-World Case Studies and Experiments**
  - **Dunbar's Number**
    - This rule suggests there is a brain limit to how many stable social relationships a human can handle.
    - *Question*: If the human brain is capable of meaningfully perceiving and processing up to "190 pair-wise relationships", what is the maximum number of people an organization should have to achieve the best interpersonal relationships?
    - *Answer*: **20**. (Because choosing pairs from 20 people results in exactly 190 combinations!).
  - **Spread of Obesity in Social Networks**
    - **Homophily**: This term refers to **"The tendency for people to choose relationships with people who have similar attributes."**
    - A person is officially defined as obese in this research if he/she has a Body Mass Index (BMI) of **`>= 30`**.
    - The highest "Probability That an Ego Will Become Obese with an Alter Who May Become Obese" was found in a relationship with a **Mutual friend**.
  - **Small World Phenomena**
    - The first ever experiment to investigate the "small world" phenomena (the idea that everyone is connected by a few steps) was conducted by **Stanley Milgram**.
  - **The Capture of Saddam Hussein**
    - The military used social network maps to track him down.
    - However, it is an INCORRECT inference to say that **Saddam Hussein was the hub of his scale-free network**. (He was actually intentionally isolated, not a hub!).
  - **Food and Recipes Networks**
    - The "flavor network" discussed in the 'Network Science' book is a **Monopartite, Weighted** graph representation of recipes data.
  - **Indian Railways Network (IRN)**
    - In a 2002 study by Sen et al., two railway stations are said to be connected/linked if **at least one train stops at both the stations**.
  - **Airport Network of India (ANI)**
    - In a 2008 study by Bagler, the link between two airports was defined as **the number of flights per week**.

- **5. Subjective Practice Problems (For deeper learning and solving)**
  - *These are subjective questions taken exactly from the source to practice solving real test scenarios.*
  - **Definitions and Illustrations**: Define and provide a simple illustration of each of the following: (a) Self-avoiding path, (b) Eulerian path, and (c) Hamiltonian path.
  - **Real-World Examples**: Write one real-world example for each of the following types of networks. Clearly state what is a node, an edge, and what constitutes the weight/direction: (a) Bipartite Networks, (b) Weighted Networks, and (c) Directed Network.
  - **Food and Recipes Constructs**: In the example of networks related to Food and Recipes, describe what the (a) mono-partite, (b) bi-partite, and (c) tri-partite networks that one could construct would look like. Clearly explain each of these networks.
  - **Algorithm Details**: Briefly explain the Breadth First Search (BFS) strategy used for finding the shortest path between nodes `i` and `j`. What is the computational complexity of the BFS algorithm?
  - **Watts and Strogatz Condition**: When implementing the Watts and Strogatz strategy, what is the condition/constraint on the 'number of nodes (n)' for generating a k-regular graph?
  - **Matrix Formalism Problem**:
    - Let `A` be the `N x N` adjacency matrix of an undirected unweighted network, without self-loops.
    - Let `1` be a column vector of `N` elements, all equal to 1. (In other words `1 = (1, 1, ..., 1)^T`, where the superscript `T` indicates the transpose operation).
    - *Task*: Use matrix formalism (multiplicative constants, multiplication row by column, matrix operations like transpose and trace, etc., but **avoid the sum symbol Σ**) to write expressions for:
      - (a) The vector `k` whose elements are the degrees `k_i` of all nodes `i = 1, 2, ..., N`.
      - (b) The total number of links, `L`, in the network.
      - (c) The number of triangles `T` present in the network, where a triangle means three nodes, each connected by links to the other two (Hint: you can use the trace of a matrix).
      - (d) The vector `k_nn` whose element `i` is the sum of the degrees of node `i`'s neighbors.
      - (e) The vector `k_nnn` whose element `i` is the sum of the degrees of node `i`'s second neighbors.
  - **Erdős-Rényi Mathematical Problem**:
    - Consider an Erdős-Rényi network with `N = 3,000` nodes, connected to each other with probability `p = 10^-3`.
    - *Tasks*:
      - (a) What is the expected number of links, `<L>`?
      - (b) Which regime does the network belong to?
      - (c) Calculate the probability `p_c` so that the network is at the critical point.
      - (d) Given the linking probability `p = 10^-3`, calculate the number of nodes `N_cr` so that the network has only one component.
      - (e) For the network in (d), calculate the average degree `<k_cr>` and the average distance between two randomly chosen nodes `<d>`.