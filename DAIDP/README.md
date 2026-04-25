# DAIVP

## nutshell
- **AI PRODUCT DESIGN: KNOWLEDGE GRAPHS VS. CONTEXT GRAPHS**
  - **Knowledge Graphs:**
    - **Definition:** Structured maps of entities (people, places, concepts) and their relationships. 
    - **Purpose:** Shows what exists and how things connect. Answers "Who/What matters".
    - **Examples:** Recommendation engines (users -> products -> reviews), Medical AI (symptoms -> diseases).
    - **Strengths:** Clear factual relationships, easy to query, supports reasoning.
    - **Limitations:** Static, does not adapt to changing situations, misses contextual nuance.
    - **Tools:** Neo4j, RDFLib, NetworkX, GraphDB, Google Knowledge Graph API, Microsoft Graph.
  - **Context Graphs:**
    - **Definition:** Dynamic maps of situational context around knowledge.
    - **Purpose:** Shows when, why, and under what conditions relationships matter.
    - **Examples:** Chatbots adapting to user tone, Travel AI adjusting to seasons/budgets.
    - **Strengths:** Flexible, adaptive, personalizes experiences.
    - **Limitations:** Harder to build, complex to maintain, needs continuous updates.
    - **Tools:** TrustGraph, Atlan, Cloud AI Platforms.
  - **Summary:** Knowledge graphs are the skeleton (structure). Context graphs are the muscles and nerves (adaptation).

- **AI SYSTEM TYPES: LLM vs RAG vs AGENTS**
  - **LLM (Large Language Model):** Smart text generator. Guesses next words. Forgets past chats. Cheap and fast, but hallucinates. Example: ChatGPT.
  - **RAG (Retrieval-Augmented Generation):** AI that searches specific documents before answering. Reads your files to give factual answers. Medium cost. Example: Company help chatbots.
  - **AI Agent:** Autonomous software that plans steps and uses tools to reach goals. Remembers past steps. Takes 3-5 days to build. Example: AutoGPT, coding assistants.
  - **Agentic AI:** A team of specialized AI workers. Share memory and coordinate tasks. Most expensive and takes weeks to build. Example: Microsoft AutoGen, CrewAI.

- **BUILDING AGENTIC AI ARCHITECTURE**
  - **Layer 1: Model / Compute Layer:** The brain. Generates text, understands audio/images, follows instructions. Tools: Ollama (runs models locally), Hugging Face, Unsloth.
  - **Layer 2: Agent / Orchestration Layer:** The logic. Handles planning, tool usage, and memory. Tools: LangChain, LangGraph.
    - **Orchestration Patterns:**
      - **Sequential:** Output of Agent A goes to Agent B.
      - **Parallel:** Agents work at the same time. Good for fact-checking.
      - **Router:** Directs tasks to specific agents based on user intent.
      - **Hierarchical:** Manager agent coordinates worker agents.
  - **Layer 3: App / Product Layer:** The user interface. Handles UI, APIs, and access control.
  - **Model Context Protocol (MCP):** A universal standard (like USB for AI) to securely connect AI to external data and tools.
  - **Function Calling:** Teaches AI to output data in structured formats like JSON so client apps can trigger APIs.

- **PRODUCT MANAGEMENT FUNDAMENTALS**
  - **Product Manager (PM):** Plans, develops, launches, and manages a product lifecycle. AI PMs must also understand data science, ethics, and act as translators between engineers and business.
  - **Goods vs. Services:** Goods are tangible and stored. Services are intangible, consumed as they are produced, and variable.
  - **Service-Dominant (S-D) Logic:** Treats customers as co-creators of value. Value is uniquely determined by the user.
  - **Product Evolution Models:**
    - **MVP (Minimum Viable Product):** Fast to build, tests ideas, low UI/UX focus.
    - **MMP (Minimum Marketable Product):** Minimum features needed to sell.
    - **MLP (Minimum Lovable Product):** Focuses on enjoyable UX to gain a loyal following.
  - **Smart Products:** Combine servitization and AI. Progress through monitoring, control, optimization, and autonomy.

- **DEFINING THE VALUE PROPOSITION**
  - **Statement Formula:** For (target customer) dissatisfied with (existing solution) due to (unmet needs), we offer a (product) that provides (key benefits).
  - **Minimum Viable Segment (MVS):** The smallest user group with identical needs so you can sell the same product repeatedly without changing it.
  - **The 4 U's of Problem Solving:** Problems must be Unworkable, Unavoidable, Urgent, and Underserved.
  - **BLAC Framework for Needs:** Needs are Blatant, Latent, Aspirational, or Critical. Best products move from nice-to-have to must-have (Critical).
  - **Defensibility (Moats):** 3Ds framework. Must be Defensible, Disruptive, and Discontinuous. Examples: Network effects, switching costs, proprietary data.
  - **Gain/Pain Ratio:** The gains (benefits, money made) must massively outweigh the pain (friction, cost, learning curve) to force users to switch.

- **HUMAN BEHAVIOR AND COGNITIVE DESIGN**
  - **Maslow’s Hierarchy in UX:** Functionality = Physiological. Reliability/Security = Safety. Usability = Belonging. Human needs always come before AI intelligence.
  - **Cognitive Load Theory:**
    - **Intrinsic Load:** The task's natural difficulty.
    - **Extraneous Load:** Bad design, clutter, and confusing UI. Designers must eliminate this.
    - **Germane Load:** Good effort that builds learning, like step-by-step guides.
  - **Media Naturalness Theory:** Humans prefer face-to-face communication. AI should use natural, conversational language to reduce mental effort.
  - **Human-in-the-Loop:** Humans must oversee critical AI decisions (e.g., medical diagnoses) to ensure safety and trust.
  - **Actor-Network Theory (ANT):** Treats humans, machines, and data as equal actors in a network.
  - **Hegel’s Dependence Paradox:** If AI does everything, humans lose skills. AI should be a partner, not just a servant.

- **AI ETHICS, PRIVACY, AND LAWS**
  - **Explainable AI (XAI):** Making AI logic clear.
    - **LIME:** Explains specific individual predictions.
    - **SHAP:** Shows how much each feature contributed to a result.
    - **GradCAM:** Highlights the part of an image that caused the AI's decision.
  - **Privacy Enhancing Technologies:**
    - **Federated Learning:** AI learns directly on user devices. Raw data never leaves the phone. Example: Apple Siri.
    - **Differential Privacy:** Adds mathematical noise so no individual user can be identified.
    - **Homomorphic Encryption:** Allows math operations on encrypted data without decrypting it.
  - **Global Regulations:**
    - **GDPR (EU):** Protects personal data, demands consent and the right to be forgotten.
    - **EU AI Act:** Risk-based rules. High-risk AI (healthcare, HR) needs strict audits.
    - **India DPDP Act 2023:** Fiduciaries must ask for consent plainly, protect data, and delete it upon request. Penalties up to ₹250 Crore for breaches.
  - **Zero Trust Security:** Never assume trust. Always verify users, AI, and apps explicitly.

- **RESEARCH AND EVALUATION METHODS**
  - **Variables:**
    - **Mediated Variables:** Explains *why* or *how* a relationship happens. It is the mechanism pathway.
    - **Moderated Variables:** Explains *when* or *for whom* a relationship happens. It changes the strength or direction.
  - **Literature Search:** Finding papers to learn gaps, methods, and existing problems. Use Google Scholar, ACM DL, IEEE Xplore.
  - **Boolean Search:** AND (all terms), OR (any term), NOT (exclude term), "Quotes" (exact phrase).
  - **Extended Abstract:** A 1-6 page mini research paper used for conference evaluations. Contains Background, Method, Results, Figures, and Conclusion.

- **CASE STUDY: TELEMETRYTRADE AI PROJECT**
  - **Problem:** Retail stock and crypto traders suffer from fragmented tools, information overload, and hallucinating AI chatbots.
  - **Target Audience:** Active Traders (need fast charts and verified info) and Small Quant Funds (need affordable API access).
  - **Solution / Features:**
    - **Real-Time Charting:** Stocks, crypto, and forex on one screen.
    - **Verified RAG Research:** Answers sourced directly from financial filings with clickable citations. Zero hallucinations.
    - **Portfolio AI:** Uses OCR to read broker screenshots and gives risk and diversification advice.
  - **Architecture:** Next.js 14 frontend, Gemini API for intelligence, CoinGecko for crypto prices, TradingView for charts, Clerk for security.
  - **Usability Test Results:** Portfolio Reviewer was highly loved (8/11 users). AI explanations were too generic and need a beginner/pro toggle. Users want stock-style fundamentals added.
  - **Business Model:** Freemium SaaS. Free charts, Pro subscription ($10-30/mo) for RAG research, and API monetization for funds.

## depth 

- **HUMAN-MACHINE INTERACTION & CORE AI CONCEPTS**
  - **Interaction Modalities:** Defined by a base medium and an action, structured as Modality -> Context -> Method. Example: optical mouse sensor becomes "finger motion tracking".
  - **Smart Objects:** Physical devices augmented with AI, like smart lights, robot pets, or Amazon Alexa.
  - **Service AI:** Technologies providing value through flexible adaptation via sensing, learning, decision-making, and actions.
  - **Trust in AI:** Composed of competence (behaves capably), integrity (behaves ethically), and benevolence (behaves fairly).
  - **Human-Centered AI (HAI):** Shifts from one-dimensional thinking to a two-dimensional framework, achieving both high human control and high computer automation.
  - **Interaction Models:**
    - **Master-Servant:** Human commands, machine executes (e.g., Alexa).
    - **Partner-Partner:** Dynamic exchange, mutual problem solving (e.g., GitHub Copilot).
    - **Trusted Advisor:** Machine proactively suggests, requiring high transparency (e.g., IBM Watsonx).
  - **Automation vs Control Matrix:** 
    - High Control / Low Automation: Manual data analysis.
    - High Control / High Automation: Ideal balance, AI automates while human guides (e.g., MS365 Copilot).
    - Low Control / High Automation: Fast but risky, system acts without human input (e.g., High-Frequency Trading).

- **VALUE PROPOSITION & PRODUCT MANAGEMENT**
  - **Value Proposition Formula:** For (target customer segment) dissatisfied with (existing solution) due to (unmet needs), we offer a (product category) that provides (key benefits).
  - **Minimum Viable Segment (MVS):** The smallest customer group sharing identical needs, allowing you to sell the exact same product repeatedly without altering it.
  - **The 4 U's of Problem Solving:** Worthwhile problems are Unworkable, Unavoidable, Urgent, and Underserved.
  - **BLAC Framework for Needs:** Needs are classified as Blatant, Latent, Aspirational, or Critical. Goal is to move products from nice-to-have to must-have (Critical).
  - **Defensibility (Moats):** Use the 3Ds: Defensible, Disruptive, Discontinuous. Examples include proprietary IP, location, network effects, switching costs, and scale economies.
  - **Gain/Pain Ratio:** Product gains must massively outweigh the friction and learning pains required to switch.
  - **Goods vs Services:** Goods are tangible, transferable, and storable. Services are intangible, uniquely experienced, variable, and consumed simultaneously as they are produced.
  - **Service-Dominant (S-D) Logic:** Treats customers as active co-creators of value, meaning value is uniquely determined by the user's context and engagement.
  - **Product Management Roles:** Managing the entire product lifecycle from ideation to launch. Requires soft skills like leadership, negotiation, communication, and decision-making.
  - **Smart Products:** Physical products augmented with sensors and AI connectivity. They progress through remote monitoring, control, optimization, and finally autonomy.
  - **Tech Evaluation of AI Startups (VDAT):**
    - **Variety in Data:** Handling infinite, chaotic inputs (e.g., visual inputs for self-driving cars).
    - **Data Acquisition:** Securing proprietary data to build a competitive "data moat".
    - **Architecture:** Building scalable systems capable of handling low-latency processing.
    - **Talent Acquisition:** Collaborating with deep domain experts.

- **COGNITIVE LOAD & HUMAN BEHAVIOR**
  - **Maslow's Hierarchy applied to UX:** Functionality equals Physiological needs, Security equals Safety, Usability equals Belonging. Human needs and feelings of safety always precede AI intelligence.
  - **Cognitive Load Theory:** If working memory overloads, learning stops.
    - **Intrinsic Load:** The natural difficulty of the task itself.
    - **Extraneous Load:** Confusing UI, messy code, bad presentation. Designers must eliminate this.
    - **Germane Load:** Effort that actively builds understanding, like step-by-step onboarding.
  - **Media Naturalness Theory:** Humans evolved for face-to-face communication. AI should use natural, conversational cues. Deviating from naturalness increases cognitive and emotional friction.
  - **Actor-Network Theory (ANT):** Treats humans and non-human systems (AI) as equal actors. Action is distributed across a network of components.
  - **Hegel's Dependence Paradox:** The Master depends on the Servant's labor. If AI acts only as a servant doing everything, humans lose their skills. Designers must decide if AI should be a collaborative Partner instead.
  - **Anthropomorphism:** Giving AI human-like tone and feedback reduces fear and intimidation.

- **PRIVACY, ETHICS & SECURITY LAWS**
  - **Federated Learning:** AI models train directly on user devices. Raw data never leaves the device, reducing breach risks (e.g., Apple Siri, Google Gboard).
  - **Differential Privacy:** Adds mathematical noise to datasets so individual contributions remain totally hidden while statistical trends stay accurate.
  - **Global Regulations:** GDPR (Europe), HIPAA (Healthcare), CCPA (California).
  - **India DPDP Act 2023:** Requires explicit, plain-language consent for specific data categories. Fiduciaries must protect data and delete it upon request, with penalties reaching up to ₹250 Crore.
  - **EU AI Act Risk Tiers:**
    - **Unacceptable:** Social scoring, biometric categorization.
    - **High Risk:** Healthcare devices, recruitment software, critical infrastructure.
    - **Limited Risk:** Chatbots, deepfakes (require transparency).
    - **Low Risk:** AI video games, spam filters.
  - **Privacy by Design (PbD):** Seven principles including proactive protection, privacy as default, embedded privacy, end-to-end security, and full functionality.
  - **OWASP Security:** Global standard for web application security. Key vulnerabilities include Broken Access Control, Injection, and Cryptographic Failures. Hidden UI routes violate OWASP A01. Sensitive data (PHI) must use masked variants.

- **EXPLAINABLE AI (XAI)**
  - **Definition:** Making black-box AI logic clear so humans can understand the solution. Deep learning has high accuracy but low explainability, while decision trees have high explainability but lower accuracy.
  - **Feature Importance:** Identifies the variables contributing most to a prediction.
  - **LIME:** Explains individual, localized predictions.
  - **SHAP:** Assigns a specific contribution value to every single feature.
  - **GradCAM:** Visualizes and highlights the specific part of an image that triggered an AI decision.

- **AI DESIGN GUIDELINES & MENTAL MODELS**
  - **IBM Carbon:** Uses distinct visual AI labels and progressive explainability (layering information from What -> Why -> How).
  - **Emplifi Soul (8 Patterns):** User-Initiated, Contextual, Predictive, Conversational, Search, Automated workflows, Augmented Decision Making, and Collaborative AI.
  - **SAP Fiori:** Enterprise focus on role-based explanations, high-stakes traceability, and progressive disclosure to support audits.
  - **PatternFly:** Focuses on augmenting human ability (not replacing it), verifying outputs, mitigating bias, and handling errors gracefully.
  - **Microsoft HAX Toolkit:** 18 guidelines across the user journey (e.g., make clear what the system can do, support efficient correction, learn from user behavior).
  - **Mental Models:**
    - **Human-in-the-Loop:** Human oversight is mandatory at critical decision points.
    - **Occam's Razor:** Favor simple design paths over over-engineered AI logic.
    - **Systems Thinking:** Consider AI's ripple effect across the whole ecosystem.
    - **AI as Electricity:** AI is a foundational technology enabling entirely new innovations.
    - **Designing for Possibilities:** Don't design rigid user flows (like a train track); design open-ended tools (like a chef's kitchen) to handle infinite degrees of user freedom.

- **AGENTIC AI ARCHITECTURE & TOOLS**
  - **Models vs Agents:** Models guess text based on static training and forget past chats. Agents have tools, memory, and orchestration logic to dynamically interact with the world and execute multi-step plans.
  - **Three Architectural Layers:**
    - **Model/Compute Layer:** The core brain that generates text and processes embeddings. Tools: Ollama, Hugging Face, Unsloth.
    - **Agent/Orchestration Layer:** Handles reasoning, memory, tool usage, and routing. Frameworks: LangChain, LangGraph.
    - **App/Product Layer:** The user interface, API connections, and access control (e.g., Next.js).
  - **Orchestration Patterns:**
    - **Sequential Chain:** Agent A output feeds Agent B input.
    - **Parallel Execution:** Agents work simultaneously (great for fact-checking).
    - **Router Pattern:** Central agent directs tasks to specific specialists.
    - **Hierarchical:** A manager agent delegates to worker agents.
    - **Collaborative:** Agents negotiate to reach consensus.
  - **Connecting to the World:**
    - **Extensions:** APIs executed directly on the agent side.
    - **Function Calling:** The AI outputs structured JSON instructions, but the client-side application manually executes the API call.
    - **Data Stores (RAG):** Retrieval-Augmented Generation connects the AI to fresh data (PDFs, sites) via vector databases, grounding answers in reality.
    - **Model Context Protocol (MCP):** A universal, standardized protocol (like USB for AI) letting agents connect to data sources securely.
  - **Failure Modes:** Systems break via infinite reasoning loops, hallucinated tool usage, or incorrect routing. Prevent this by limiting reasoning steps, validating outputs, and using reviewer agents.

- **RESEARCH METHODOLOGY & LITERATURE SEARCH**
  - **Goal:** To understand existing problems, identify gaps, and frame research questions.
  - **Tools:** Google Scholar, Semantic Scholar, ACM DL, IEEE Xplore.
  - **Boolean Search:** AND (requires all terms), OR (requires any term), NOT (excludes terms), "Quotes" (exact phrase matching).
  - **Top Venues:** CHI, TOCHI. They reflect the community's gold standard for problem framing and methodology.
  - **Paper Structure:** Abstract, Introduction, Related Work, Method, Results, Discussion, Conclusion.
  - **Abstract:** 150-250 word single paragraph summarizing the problem, method, and results. Must be Concise, Clear, Complete, and Cohesive (4 C's).
  - **Extended Abstract:** 1-6 page mini research paper used for conference evaluations, incorporating background, methods, results, and figures.

- **CASE STUDY: TELEMETRYTRADE AI**
  - **Problem:** Retail traders face information overload and rely on hallucination-prone chatbots. Currently requires 7 open tabs to place a single trade.
  - **Solution:** A unified AI platform functioning as the "Bloomberg for Retail Traders".
    - **Real-Time Charting:** Multi-asset views (crypto, stocks).
    - **Verified RAG Research:** Analyzes 10-K filings with zero hallucinations and clickable citations.
    - **Portfolio AI:** Uses OCR to read broker screenshots and generates instant risk and diversification analysis.
  - **Target Personas:** Time-poor active retail traders and programmatic small quant funds.
  - **Business Model:** Freemium SaaS. Free charting -> Pro subscription ($10-30/mo) -> Portfolio AI add-on -> Enterprise API limits ($99-299/mo).
  - **Usability Testing Results:** Portfolio Reviewer was highly praised (8/11 would use). However, AI explanations were too generic, requiring a "Beginner/Trader/Pro" depth toggle. Token Discovery required curated shelves rather than raw filters.

