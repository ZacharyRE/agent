### Relevant Research 📑

1. [Godel Agent: A Self-Referential Agent Framework for Recursively Self-Improvement 📄](https://arxiv.org/pdf/2410.04444) *(arXiv 2024)*
2. [Reflexion: Language Agents with Verbal Reinforcement Learning 📄](https://arxiv.org/pdf/2303.11366) *(arXiv 2023)*
3. [AgentBoard: An Analytical Evaluation Board of Multi-turn LLM Agents 📄](https://arxiv.org/pdf/2401.13178) *(arXiv 2024)*
4. [Evaluation Agent: Efficient and Promptable Evaluation Framework for Visual Generative Models 📄](https://arxiv.org/pdf/2412.09645) *(arXiv 2024)*
5. [Reflective Multi-Agent Collaboration based on Large Language Models 📄](https://proceedings.neurips.cc/paper_files/paper/2024/file/fa54b0edce5eef0bb07654e8ee800cb4-Paper-Conference.pdf) *(NeurIPS 2024)*




# Order Sensitivity in Hand-Designed Agents

## 🌟 Motivation
Large Language Model (LLM) agents are often constructed using **hand-designed strategies**, such as:
- Chain-of-Thought (CoT)
- Self-Consistency (SC)
- Reflexion
- Debate
- Step-back Reasoning

These strategies are usually combined in **ad-hoc pipelines**, where the **initial strategy** and the **execution order** are manually chosen.

👉 However, **does the order of these strategies matter?**  
👉 Can different orders lead to significantly different performances?  
👉 If so, how can we quantify and optimize it?

---

## 🔍 Research Idea
We propose a systematic study on the **order sensitivity** of hand-designed agents.  
Specifically, we will investigate:

1. **Initial Strategy Effect**  
   - How does the choice of the first step (e.g., CoT vs ToT) influence downstream performance?

2. **Order Effect**  
   - Does the sequence of applying strategies (e.g., CoT → SC → Reflexion vs SC → CoT → Reflexion) significantly change accuracy, cost, or robustness?

3. **Order Sensitivity Index (OSI)**  
   - A new metric to quantify how much performance varies across different orderings of the same strategy set.

---

## 📐 Formalization
Let \(O = \{o_1, o_2, ..., o_k\}\) be a set of strategies.  
For each permutation \(P\) of \(O\), the pipeline performance is \(Acc(P)\).

We define the **Order Sensitivity Index (OSI)** as:

\[
\text{OSI}(O) = \frac{\max_{P} Acc(P) - \min_{P} Acc(P)}{\text{mean}_{P} Acc(P)}
\]

- **High OSI** → performance is highly sensitive to order.  
- **Low OSI** → order has little effect (robust).  

---

## 🧪 Experimental Plan
- **Benchmarks**: DROP (RC), MGSM (Math), MMLU (General), HumanEval (Code), BBH (Reasoning)  
- **Operators**: CoT, SC, Reflexion, Debate, Step-back  
- **Evaluation Metrics**: Accuracy, Variance, Cost (# of LLM calls), Robustness against adversarial prompts  

We will:
1. Run all possible orderings of 2-step and 3-step pipelines.  
2. Compute OSI for each task and operator set.  
3. Analyze cross-task trends and sensitivity patterns.  

---

## 🧠 Theoretical Analysis
We aim to explain **why order matters** via:
1. **Error Propagation Model**  
   - Different orders affect how errors are corrected or amplified.  
2. **Information-Theoretic View**  
   - Each strategy changes the entropy of the solution space (expand, compress, shift).  
   - The order of entropy operations influences final accuracy.  
3. **Cognitive Analogy**  
   - Like human reasoning: "diverge → converge" (brainstorm then refine) vs "converge → diverge" (lock in too early) yield different outcomes.

---

## 🚀 Contributions
- **Empirical Insight**: First systematic study of order sensitivity in hand-designed LLM agents.  
- **New Metric**: Order Sensitivity Index (OSI).  
- **Theoretical Framework**: Information-theoretic and error-propagation explanation.  
- **Optimization**: Towards automated search for optimal strategy order.  

---

## 📌 Next Steps
- Implement OSI computation toolkit.  
- Release benchmark results across multiple tasks.  
- Explore **meta-controller** to automatically find optimal ordering.

---

## 📚 References
- Wei et al., *Chain-of-Thought Prompting* (NeurIPS 2022)  
- Shinn et al., *Reflexion: Language Agents with Verbal Reinforcement Learning* (NeurIPS 2023)  
- Liang et al., *LLM Debate* (ICLR 2024)  
- Hu et al., *Meta Agent Search* (NeurIPS 2024)  
