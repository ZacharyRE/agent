# Value-Ensemble Agents: Persona-Aligned Multi-Agent Decision Making


## 🌍 Introduction
Artificial Intelligence agents often optimize for a single objective, 
but real-world human decision-making is inherently **value-driven** and involves **trade-offs**.  
For example:  
- **Safety vs. Efficiency** (driving slower but safer vs. faster but riskier)  
- **Creativity vs. Stability** (innovative but risky vs. conventional but reliable)  

We propose a **Persona + Ensemble Multi-Agent framework**, where each agent is assigned a distinct human value perspective (e.g., **Safety**, **Creativity**, **Efficiency**).  
By dynamically weighting their contributions, the system can make **balanced, human-centered decisions** in complex scenarios.


---

## 🚀 Motivation
- Current LLMs and agents lack **value-awareness**.  
- Ensemble methods improve accuracy but rarely consider **human values**.  
- Human-centered decision-making requires **balancing conflicting perspectives** rather than optimizing a single one.  

Our approach:  
**Ensemble of Value-Aligned Agents → Dynamic Weighting → Balanced Decision Output**

---

## 🧠 Method
1. **Value Assignment**  
   - Each agent is associated with a specific value dimension.  
   - Example: `Safety-Agent`, `Creativity-Agent`, `Efficiency-Agent`.  

2. **Decision Collection**  
   - All agents provide outputs for a given task.  

3. **Dynamic Weighting**  
   - Weights are adjusted based on task context, user preference, or reward signals.  
   - Approaches: heuristics, reinforcement learning, meta-learning.  

4. **Final Decision**  
   - Weighted aggregation produces the **Value-Ensemble Decision**.  

> Conceptually, this can be visualized as a triangle:  
> - Vertices = Safety, Creativity, Efficiency  
> - Center = Final Decision (weighted by context)

---

## 📊 Benchmarks
We plan to evaluate on both **our benchmarks** and **public datasets**:

- ✅ **VIVA** – Vision-grounded decision-making with human values  
- ✅ **HRDBench** – Human-centered embodied reasoning benchmark  
- ✅ **ETHICS, Social Chemistry 101, Moral Stories** – Moral/value-based reasoning  
- ✅ **SafeBench** – Safety-critical scenarios  
- ⚙️ Future: Extend general benchmarks (e.g., Social IQa, MMMU) with **value annotations**

---

## 🔎 Preliminary Results
*(Work in Progress)*  
- Initial experiments show that Value-Ensemble agents produce **more stable and balanced outputs** compared to single models.  
- More detailed results will be released soon.  

---

## 📌 Roadmap
- [ ] Proof-of-Concept implementation (static weighting)  
- [ ] Dynamic weighting with reinforcement learning  
- [ ] Evaluation on ETHICS & Social Chemistry  
- [ ] Visualization of value trade-offs (Pareto frontier analysis)  
- [ ] Release paper preprint  

---

