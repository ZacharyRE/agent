# Value-Ensemble Agents: Persona-Aligned Multi-Agent Decision Making

## 🌍 Introduction
Artificial Intelligence agents often optimize for a single objective, 
but real-world human decision-making is inherently **value-driven** and involves **trade-offs**.  
For example:  
- **Safety vs. Efficiency** (driving slower but safer vs. faster but riskier)  
- **Creativity vs. Stability** (innovative but risky vs. conventional but reliable)  

We propose a **Persona + Ensemble Multi-Agent framework**, where each agent represents a **persona-aligned value dimension** (e.g., *Safety*, *Creativity*, *Efficiency*).  
A learnable **Ensemble Aggregator** then assigns dynamic weights to combine their outputs into a **balanced, human-centered decision**.

---

## 🚀 Motivation
- Current LLMs and agents lack **value-awareness**.  
- Traditional Ensemble methods improve performance, but rarely consider **conflicting human values**.  
- Human-centered decision-making requires balancing multiple perspectives rather than optimizing a single one.  

**Key idea:**  
*Personas inject value priors → Multiple agents explore diverse solutions → Ensemble aggregates with context-aware weights.*

---

## 🧩 Architecture (Persona + Ensemble)

```mermaid
flowchart LR
    A[Task / Context] --> P1[Persona: Safety-Agent]
    A --> P2[Persona: Creativity-Agent]
    A --> P3[Persona: Efficiency-Agent]
    P1 --> W[Ensemble Aggregator]
    P2 --> W
    P3 --> W
    A -->|Signals: user prefs, risk level, feedback| W
    W --> F[Final Decision (y_hat)]

