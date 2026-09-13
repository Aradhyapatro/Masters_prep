# The Complete AI Mastery Curriculum
### A self-study program modeled on ASU's MS in Artificial Intelligence

---

## How this maps to ASU's actual program

ASU's MS in AI is built from: a **core of foundational AI courses**, electives drawn from **three streams** (statistical learning; embodied AI, cognition & perception; reasoning & decision-making), and a **culminating research/applied project**. This curriculum mirrors that shape, but adds a Foundations phase (math + programming) that ASU assumes you already have via admissions prerequisites, since you're starting from scratch.

**Total time estimate:** 12–18 months at 15–20 hrs/week if you have some programming background; 18–24 months if starting fully from zero.

**On theory vs. implementation:** every module below pairs a "learn it" resource with a "build it" resource, and now also a bank of extra hands-on projects beyond the single required one. The rule of thumb: never move to the next module's theory until you've implemented at least one thing from the current module without copying a tutorial line-by-line. Reading and watching lectures builds recognition; building things badly and then fixing them builds the recall and debugging instinct that actually gets tested in interviews and on the job.

**Important honesty note:** This gets you the *knowledge and portfolio* of an ASU AI master's graduate. It does not confer a degree, transcript, or accreditation — those require enrollment. If the credential itself matters for your career (visa sponsorship via CPT/OPT, HR degree filters, faculty jobs), you'll eventually need the actual degree; this curriculum is an excellent complement or a way to test the field before paying tuition.

---

## Module 0 — Foundations (6–10 weeks)

*ASU assumes this via admission requirements (calculus, linear algebra, programming, data structures). Skip sections you already have.*

**0.1 Programming**
- Python fluency: data structures, OOP, NumPy, Pandas, virtual environments, git
- Project: build a small data-processing pipeline from a messy CSV to a clean analysis
- **Resources:**
  - [Python for Everybody](https://www.py4e.com/) — free, full course + book, best if you've never coded before
  - [Automate the Boring Stuff](https://automatetheboringstuff.com/) — free online book, fastest path to "useful Python" if you already think like a programmer
  - [NumPy Quickstart](https://numpy.org/doc/stable/user/quickstart.html) + [Pandas 10 Minutes](https://pandas.pydata.org/docs/user_guide/10min.html) — official docs, skim once you've done a project or two

**0.2 Data Structures & Algorithms**
- Arrays, trees, graphs, hash maps, sorting/searching, Big-O
- Project: solve 50 algorithm problems, timed
- **Resources:**
  - [CS 61B (Berkeley)](https://cs61b.berkeley.edu/) — free full course with lectures, labs, and projects; the most rigorous free option
  - [NeetCode 150](https://neetcode.io/practice) — curated interview-style problem set with free video walkthroughs; better for drilling than for first learning
  - [VisuAlgo](https://visualgo.net/en) — free animated visualizations of algorithms, great for building intuition before coding

**0.3 Math for AI**
- Linear algebra: vectors, matrices, eigenvalues/eigenvectors, SVD
- Calculus: derivatives, gradients, chain rule, partial derivatives
- Probability & statistics: distributions, Bayes' theorem, MLE, hypothesis testing
- Project: implement gradient descent and PCA from scratch in NumPy (no libraries)
- **Resources:**
  - [3Blue1Brown — Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra) — free video series, best intuition-builder that exists for this topic
  - [3Blue1Brown — Essence of Calculus](https://www.3blue1brown.com/topics/calculus) — same, for calculus; watch before doing any formal course
  - [MIT 18.06 Linear Algebra (Gilbert Strang)](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/) — free OCW, full rigor with problem sets, go here after 3Blue1Brown
  - [Khan Academy — Statistics & Probability](https://www.khanacademy.org/math/statistics-probability) — free, self-paced, good for filling specific gaps rather than start-to-finish

**Hands-on project bank (do 2–3, not just the one above):**
- Rebuild `train_test_split`, a k-fold cross-validator, and a confusion-matrix function from scratch — no sklearn
- Implement linear regression via normal equations AND via gradient descent, confirm they converge to the same answer
- Write a tiny autodiff engine (10 ops: add, mul, pow, relu, etc.) that computes gradients automatically — this is the single best exercise for making backprop click
- Take a real messy dataset (e.g. NYC 311 complaints, or any dataset from [data.gov](https://www.data.gov/)) and produce a cleaned CSV + a 1-page EDA notebook
- Enter a "getting started" Kaggle competition (Titanic, House Prices) using only pandas/numpy, no ML libraries yet

**Checkpoint:** You should be able to derive backpropagation for a 2-layer network on paper AND reproduce it in code without looking anything up.

---

## Module 1 — AI Foundations Core (ASU's required core) (6–8 weeks)

Mirrors ASU's required foundational AI courses (search, knowledge representation, intro ML, statistics for AI).

- Intelligent agents, search algorithms (BFS/DFS, A*, minimax, alpha-beta pruning)
- Knowledge representation & logic (propositional/first-order logic, constraint satisfaction)
- Probabilistic reasoning: Bayesian networks, Markov models, HMMs
- Introduction to machine learning: supervised vs. unsupervised, bias-variance tradeoff, evaluation metrics
- Project: build a Pac-Man search/game-playing agent (CS188's classic project) and a Bayesian network for a diagnostic reasoning task
- **Resources:**
  - [CS188 Berkeley — Intro to AI](https://inst.eecs.berkeley.edu/~cs188/) — free lectures, slides, and the actual Pac-Man programming projects; the backbone of this module
  - *Artificial Intelligence: A Modern Approach* (Russell & Norvig) — the standard textbook; an [older edition PDF](http://aima.cs.berkeley.edu/) is hosted on the official companion site for reference
  - [Stanford CS221 (Percy Liang)](https://stanford-cs221.github.io/autumn2023/) — free lecture notes, good second pass on search/logic if CS188 alone doesn't stick

**Hands-on project bank:**
- Extend the Pac-Man project: implement A* with a custom admissible heuristic and benchmark node-expansion counts against BFS/DFS/UCS
- Build a Sudoku solver using constraint satisfaction (backtracking + arc consistency)
- Build a simple diagnostic expert system (e.g. medical symptom checker toy) with a hand-built Bayesian network in `pgmpy`
- Write a minimax + alpha-beta agent for Connect Four or Tic-Tac-Toe, then benchmark pruning's speedup
- Implement an HMM from scratch (forward-backward + Viterbi) for a toy POS-tagging task

---

## Module 2 — Statistical Learning Stream (10–12 weeks)

*One of ASU's three official elective streams.*

- Linear & logistic regression, regularization (L1/L2)
- Decision trees, random forests, gradient boosting (XGBoost/LightGBM)
- SVMs, kernel methods
- Unsupervised learning: k-means, hierarchical clustering, GMMs, PCA/t-SNE/UMAP
- Model evaluation: cross-validation, ROC/AUC, precision-recall, fairness metrics
- Deep learning core: feedforward networks, CNNs, RNNs/LSTMs, transformers, optimization (Adam, batch norm, dropout)
- Project: Kaggle competition (tabular) + an image classifier trained from scratch + a fine-tuned transformer for text classification
- **Resources:**
  - [An Introduction to Statistical Learning (ISLR)](https://www.statlearning.com/) — free official PDF, the best first textbook on classical ML, has R and Python labs
  - [Andrew Ng — Machine Learning Specialization](https://www.coursera.org/specializations/machine-learning-introduction) — Coursera, paid for certificate but audit-free; still the clearest teacher for ML intuition
  - [Deep Learning](https://www.deeplearningbook.org/) (Goodfellow, Bengio, Courville) — free full text online, the standard reference, dense — use for depth, not first pass
  - [fast.ai — Practical Deep Learning for Coders](https://course.fast.ai/) — free, top-down "build first, theory after" approach, excellent complement to Goodfellow's bottom-up style
  - [CS231n (Stanford)](http://cs231n.stanford.edu/) — free lecture notes and assignments, the canonical CNN/vision-and-DL-fundamentals course
  - [Andrej Karpathy — Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) — free video series that builds backprop, a tokenizer, and a GPT from raw Python; the best "implementation" companion to Goodfellow's theory
  - [Kaggle](https://www.kaggle.com/) — free datasets, competitions, and notebooks; also has short applied [micro-courses](https://www.kaggle.com/learn)

**Hands-on project bank:**
- Implement logistic regression, a decision tree, and k-means entirely from scratch in NumPy before ever calling sklearn
- Build a full XGBoost/LightGBM pipeline on a real tabular dataset (e.g. a Kaggle "Playground Series" competition) with proper cross-validation and feature engineering; write up what moved the leaderboard score and why
- Train a CNN from scratch (no pretrained weights) on CIFAR-10, then fine-tune a pretrained ResNet on the same data and compare accuracy/training time
- Fine-tune a small transformer (DistilBERT) for text classification on a real dataset (e.g. tweet sentiment, news category) using Hugging Face `Trainer`
- Recreate one classic paper's core result at small scale — e.g. train a tiny char-level RNN language model on Shakespeare text and compare to a tiny transformer on the same data
- Do a full "MLOps-lite" version of one project: track experiments with MLflow or Weights & Biases, log metrics, and compare 5+ hyperparameter configs

---

## Module 3 — Embodied AI, Cognition & Perception Stream (10–12 weeks)

*ASU's second stream.*

- Computer vision: image processing, object detection (YOLO family), segmentation, vision transformers
- Robotics & control basics: kinematics, PID control, SLAM fundamentals
- Reinforcement learning: MDPs, Q-learning, policy gradients, actor-critic, deep RL (DQN, PPO)
- Cognitive science angle: attention, memory models, human-in-the-loop AI
- Project: train an RL agent to solve a control task (CartPole → LunarLander → a custom Gym environment); build an object-detection pipeline on a real dataset
- **Resources:**
  - [David Silver — Reinforcement Learning Course (DeepMind/UCL)](https://www.davidsilver.uk/teaching/) — free lecture videos + slides, the standard RL course taught by one of AlphaGo's creators
  - [Sutton & Barto — Reinforcement Learning: An Introduction](http://incompleteideas.net/book/the-book-2nd.html) — free official PDF, the RL textbook essentially everyone in the field learned from
  - [OpenAI Spinning Up in Deep RL](https://spinningup.openai.com/) — free, code-first, pairs algorithm explanations with working implementations
  - [Gymnasium (maintained fork of OpenAI Gym)](https://gymnasium.farama.org/) — the environments you'll actually train agents in (CartPole, LunarLander, etc.)
  - [CS231n (Stanford)](http://cs231n.stanford.edu/) — reuse from Module 2 for the vision/detection half of this module
  - [Ultralytics YOLO docs](https://docs.ultralytics.com/) — free, practical guide for the object-detection project

**Hands-on project bank:**
- Implement tabular Q-learning from scratch on FrozenLake before touching any deep RL library, so you feel the Bellman update by hand
- Implement DQN from scratch (not a library wrapper) on CartPole, then swap in a library implementation (Stable-Baselines3) and confirm it matches
- Train a PPO agent on LunarLander, then a custom Gymnasium environment you design yourself (even something simple like a grid-world delivery robot)
- Fine-tune YOLOv8 on a custom-labeled dataset you build yourself (label ~200 images with a free tool like [CVAT](https://www.cvat.ai/) or [Roboflow](https://roboflow.com/))
- Build a simple SLAM demo or a PID line-follower in a simulator (e.g. PyBullet or Webots) if you want the robotics angle to be more than reading
- Combine RL + vision: train an agent on an Atari game from raw pixels using a CNN policy network

---

## Module 4 — Reasoning & Decision-Making Stream (8–10 weeks)

*ASU's third stream.*

- Natural language processing: tokenization, embeddings, sequence models, transformer architecture deep-dive, LLM fine-tuning (LoRA/PEFT), retrieval-augmented generation
- Multi-agent systems & game theory basics
- Planning under uncertainty: POMDPs, decision theory
- Causal inference fundamentals
- Project: build a RAG-based Q&A system over a custom document set; fine-tune an open-weight LLM on a domain-specific task
- **Resources:**
  - [Speech and Language Processing (Jurafsky & Martin)](https://web.stanford.edu/~jurafsky/slp3/) — free draft chapters, the standard NLP textbook, actively updated for the LLM era
  - [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course) — free, hands-on, teaches transformers via their own library; the most direct path to being able to fine-tune models
  - [CS224n (Stanford)](http://web.stanford.edu/class/cs224n/) — free lecture notes and assignments, deeper theory behind the Hugging Face course
  - [Hugging Face PEFT docs](https://huggingface.co/docs/peft/index) — free, covers LoRA and other fine-tuning methods you'll use for the capstone-adjacent project
  - [LangChain](https://python.langchain.com/) or [LlamaIndex](https://docs.llamaindex.ai/) docs — free, either works as the RAG framework for the Q&A project

**Hands-on project bank:**
- Build a transformer from scratch (attention, positional encoding, multi-head, the whole block) and train it on a toy sequence task before using any library transformer — Karpathy's "nanoGPT" walkthrough (from Module 2's resources) is the reference implementation to work from, not copy
- Build a RAG pipeline end-to-end: your own chunking strategy, an embedding model, a vector store (FAISS or Chroma), and an evaluation set of 20+ Q&A pairs you grade by hand for correctness
- Fine-tune an open-weight LLM (e.g. Llama 3 8B or a smaller model) with LoRA on a niche domain dataset (legal clauses, your own notes, a customer-support corpus) and measure before/after quality
- Build a small multi-agent system (e.g. two LLM agents that negotiate, or a planner agent + executor agent) using a framework like LangGraph or from raw function calls
- Ship the RAG or fine-tuned model behind a simple API and a minimal front end so it's a demo-able product, not just a notebook

---

## Module 5 — AI Systems, Ethics & Deployment (6 weeks)

*Mirrors ASU's AI ethics/social responsibility requirement and practical deployment skills employers expect.*

- MLOps: experiment tracking, model versioning, CI/CD for ML, serving (FastAPI/Docker), monitoring for drift
- AI safety & alignment basics: robustness, interpretability, red-teaming
- Ethics, fairness, and social responsibility: bias auditing, privacy (differential privacy basics), governance frameworks
- Project: take one earlier model to production — containerize it, serve it via an API, add monitoring and a fairness audit
- **Resources:**
  - [Full Stack Deep Learning](https://fullstackdeeplearning.com/) — free course, covers the whole deployment lifecycle (tracking, serving, monitoring) that academic courses usually skip
  - *Designing Machine Learning Systems* (Chip Huyen) — paid book, but the closest thing to an industry-standard reference on ML systems design; worth buying even if everything else is free
  - [FastAPI docs](https://fastapi.tiangolo.com/) + [Docker docs](https://docs.docker.com/get-started/) — free, what you'll actually use to serve the model
  - [Google's People + AI Guidebook](https://pair.withgoogle.com/guidebook/) — free, practical framework for fairness/UX considerations in deployed AI
  - [Anthropic's Alignment research index](https://www.anthropic.com/research) and [DeepMind Safety blog](https://deepmindsafetyresearch.medium.com/) — free, best way to track current thinking on safety/alignment rather than relying on a static textbook

**Hands-on project bank:**
- Take your Module 2 image classifier or Module 4 RAG app and fully productionize it: Dockerize it, serve via FastAPI, add request logging, and deploy it somewhere real (Render, Fly.io, or AWS/GCP free tier)
- Set up a CI pipeline (GitHub Actions) that runs tests and retrains/re-validates a model on push
- Build a basic drift-monitoring dashboard: log incoming feature distributions vs. training distribution, alert when they diverge
- Run a fairness audit on one of your earlier models using a real toolkit ([Fairlearn](https://fairlearn.org/) or [AIF360](https://aif360.res.ibm.com/)) and write up the findings like a stakeholder memo, not a notebook
- Do a small red-teaming exercise on your own RAG/LLM app from Module 4: try to get it to hallucinate, leak system instructions, or produce an unsafe output, then patch it

---

## Module 6 — Capstone / Research Project (8–12 weeks)

*Mirrors ASU's culminating experience (applied project or thesis).*

Choose one:
- **Applied project:** identify a real problem, build an end-to-end AI system, write it up like a technical report
- **Research project:** pick an open problem, read 15–20 papers, run original experiments, write a paper in NeurIPS/ICML format, consider posting to arXiv
- **Resources:**
  - [arXiv.org (cs.AI / cs.LG / cs.CL sections)](https://arxiv.org/list/cs.LG/recent) — free, where you'll source papers and optionally publish
  - [Papers With Code](https://paperswithcode.com/) — free, pairs papers with their actual implementations, invaluable for reproduction work
  - [NeurIPS style files / author guidelines](https://neurips.cc/Conferences/2024/PaperInformation/StyleFiles) — free, the formatting standard to write your report in if you want it to look like real research
  - [Papers We Love](https://paperswelove.org/) or Andrej Karpathy's [paper walkthroughs](https://www.youtube.com/@AndrejKarpathy) — free, models good practice for reading and explaining a paper

**Hands-on framing that makes this employer-legible:**
- Pick a capstone topic that doubles as a portfolio centerpiece for the job titles you're targeting (see Module 7) — e.g. a RAG system for Applied AI Engineer roles, an ML pipeline for Data Scientist roles, an RL project for Research Engineer roles
- Reproduce at least one paper's core result from scratch (not from the authors' repo) as part of the process — this is the single strongest "I can actually do research" signal on a resume
- Write the report in two forms: the formal paper/technical report, AND a 1500-word blog post version aimed at a hiring manager, not a reviewer

Deliverables that make this "portfolio-equivalent" to a master's:
1. A GitHub portfolio with 6–8 substantial projects (one per module)
2. One polished capstone with a written report or paper
3. A personal technical blog documenting what you built and learned (signals depth to employers far better than a claim of "self-taught master's")

---

## Module 7 — US Job Market Readiness (ongoing, start by Month 10–12)

*Not part of ASU's curriculum, but essential if the goal is employment in the US AI/ML market. Run this in parallel with Modules 4–6, not after — job searches take 2–4 months even once you're ready, so start the visible parts (portfolio, LinkedIn, networking) early.*

**7.1 Target roles and how they map to what you built**
- **Data Scientist** — Module 2 (stats, classical ML, experimentation) is your core evidence
- **Machine Learning Engineer** — Modules 2 + 5 (models + how you shipped them)
- **Applied AI / GenAI Engineer** — Module 4 (RAG, fine-tuning, LLM apps) — currently the hottest US hiring category
- **MLOps / ML Platform Engineer** — Module 5, with extra depth on Docker/Kubernetes/CI-CD
- **Research Engineer / Applied Scientist** — Module 6 capstone quality matters most here; these roles often still prefer a PhD or published work, so lead with reproduced papers
- **Computer Vision / Robotics Engineer** — Module 3

**7.2 Resume and portfolio**
- Build an ATS-parseable resume: standard section headers, no tables/graphics/columns that parsers mangle, plain text export tested against a free ATS checker (e.g. Jobscan)
- Quantify every bullet where possible: "improved F1 from 0.71 to 0.84," "cut inference latency 40% via quantization," not "worked on a model"
- One-page resume even with a self-taught background; length signals seniority, not effort
- GitHub: pin your best 4–6 repos, each with a real README (problem, approach, results, how to run it) — a repo with no README is invisible to a recruiter skimming for 30 seconds
- A simple personal site or blog (GitHub Pages is free) linking the portfolio, capstone writeup, and blog posts from each module

**7.3 Technical interview prep**
- **Coding/DSA round:** keep grinding NeetCode-style problems (from Module 0.2) through the whole job search, not just at the start — this atrophies fast
- **ML/AI knowledge round:** be able to whiteboard bias-variance tradeoff, regularization, how backprop works, why attention scales the way it does, precision/recall tradeoffs — all covered in Modules 1–4, but rehearse explaining them out loud
- **ML system design round:** practice designing a full system (e.g. "design a fraud detection system" or "design a recommendation system") — *Designing Machine Learning Systems* (Module 5) and the [ML System Design interview guide by Chip Huyen](https://huyenchip.com/ml-interviews-book/) are the standard prep material
- **Take-home / case study:** many AI roles use a take-home dataset instead of live coding — your Module 2/4 projects are direct practice for this format
- **Behavioral round:** prepare 6–8 STAR-format stories (Situation, Task, Action, Result) from your projects — "tell me about a time a model underperformed and what you did" is a near-guaranteed question

**7.4 Networking and visibility (US market specifics)**
- Optimize LinkedIn: headline with target role + key skills, an "About" section that names specific tools (PyTorch, LangChain, XGBoost), and post short write-ups of each module's capstone project — recruiters search LinkedIn by keyword before they search resumes
- Contribute to a real open-source ML project (even small PRs to Hugging Face, LangChain, or a popular repo) — public commit history is a strong, low-cost credibility signal in the US market
- Attend or watch talks from applied conferences (local PyData/ODSC meetups, or free-to-watch NeurIPS/ICML workshop recordings) and mention specific ones in interviews
- Informational interviews: reach out to 2–3 people/week in target roles for 15-minute chats; in the US market this consistently outperforms cold-applying alone

**7.5 Certifications — useful but secondary**
- Portfolio + interview performance outweighs certificates for this field, but if you want a credibility signal for ATS keyword filters, the highest-value ones are: AWS Certified Machine Learning – Specialty, Google Professional ML Engineer, or Databricks certifications — treat these as a 1–2 week add-on per cert, not a curriculum in themselves

**7.6 Compensation and offer research**
- [levels.fyi](https://www.levels.fyi/) — free, the standard source for US tech compensation bands by company/level/role
- Research the specific role's leveling (e.g. "L4 ML Engineer" vs "Senior") before an offer conversation so you're not negotiating blind

**7.7 If you'll need visa sponsorship**
- If you're on a student visa (F-1), OPT/STEM-OPT extension timing matters — AI/ML degree programs typically qualify for STEM-OPT, which is part of why some employers still filter on the actual degree rather than a portfolio
- If sponsorship (H-1B, etc.) is required, search filters like "visa sponsorship available" and target companies with a track record of sponsoring (large tech, well-funded startups) — this materially narrows the applicant pool you're competing against
- This is a genuine case where the *actual* ASU degree (or another accredited program) may be worth pursuing even with this curriculum completed, since it directly affects OPT eligibility — worth weighing against the self-study path early rather than after 18 months of work

---

## Suggested pacing (18-month version)

| Months | Focus |
|---|---|
| 1–2 | Module 0 (Foundations) |
| 3–4 | Module 1 (AI Core) |
| 5–7 | Module 2 (Statistical Learning + Deep Learning) |
| 8–10 | Module 3 (Embodied AI/Perception/RL) |
| 10–18 | Module 7 (Job Market Readiness) runs in parallel from here on — portfolio, LinkedIn, networking |
| 11–13 | Module 4 (Reasoning/NLP/LLMs) |
| 14–15 | Module 5 (Systems/Ethics/Deployment) |
| 16–18 | Module 6 (Capstone) + active interviewing |

---

## How to actually validate mastery along the way

- Every module ends in a *project*, not just passive learning — build things that break, then fix them.
- Reproduce at least 2 papers from scratch (not just run someone's repo).
- Do timed problem sets, not just tutorials — comprehension without recall is fragile.
- For every hands-on project, write a short README as if a hiring manager will read it — this habit alone does most of the work of Module 7.3's portfolio prep.
- Consider actual ASU-adjacent free resources: many of ASU's foundational courses draw on the same texts and Stanford/Berkeley open courseware referenced above, so you're learning from close to the same source material.
