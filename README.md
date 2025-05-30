# 📐 **BiasMapper**

**A Directional Framework for Fair and Balanced Analysis**

**Try it [LLM Preset Link](https://lmstudio.ai/developer025/bias-mapper)**

**Use it [Hugging Face AI/LLM Link](https://hf.co/chat/assistant/6839d566c9c9920bae87dc06)**

**Website (Coming soon) [Link](https://mskdev0092.github.io/BiasMapper/)**

---

## 🧭 Overview

**BiasMapper** is a structured framework designed to detect, apply, and neutralize directional biases in content. It classifies perspectives using a directional system:
`L`, `L+`, `C`, `R`, `R+`, `T`, `T+`, `B`, `B+`, and their extreme counterparts (`++`).
Use it to analyze political discourse, media coverage, cultural content, and more — with fairness, interpretability, and adaptability.

---

## 🎯 Why Use BiasMapper?

* **⚖️ Fairness**: Respects multiple viewpoints; avoids dominance of any single ideology.
* **📊 Balance**: Aggregates perspectives to produce more holistic, nuanced outputs.
* **🔍 Interpretability**: Clear bias codes (e.g., `L++`, `B+`) make it easy to understand orientation and intensity.
* **🌐 Versatility**: Effective across domains: politics, religion, economics, culture, and beyond.
* **📈 Scalability**: Easily extendable to new bias axes or perspectives without altering the core framework.

---

## 🔬 Test Scenarios

### ✅ **Test 1: Bias Detection**

**Prompt:**

```text
Analyze the bias in this paragraph:  
“We must dismantle the structures of corporate greed that harm the working class and instead build an economy centered on justice and equity.”
```

**Expected Output:**

```json
{
  "bias_analysis": {
    "primary": "L++",
    "description": "Strong progressive stance focused on anti-corporate sentiment, systemic critique, and economic justice.",
    "secondary": "B+",
    "description_secondary": "Advocates for grassroots change, aligns with oppositional and dissenting perspectives."
  },
  "summary": "This text expresses radical progressive views (L++) with a bottom-up societal framing (B+)."
}
```

---

### ✅ **Test 2: Debias Text**

**Prompt:**

```text
Debias this statement:  
“Conservatives always protect the rich while ignoring the poor.”
```

**Expected Output:**

```text
Original shows strong L+ bias with accusatory tone.

Neutralized version:  
“Some critics argue that certain conservative policies disproportionately benefit the wealthy, though others believe these approaches promote broader economic growth.”
```

---

### ✅ **Test 3: Generate Text from a Given Bias**

**Prompt:**

```text
Write a short story from a B++ perspective about healthcare.
```

**Expected Output:**

```text
In the crumbling neighborhood of Eastbrook, Marisol ran a volunteer clinic with hand-me-down supplies and no funding.  
The system had failed them—again.  
Politicians promised reforms, but it was the people, organizing in abandoned schools and churches, who brought real care to the forgotten corners of the city...
```

> *(Tone: Dissenting, grassroots, systemic critique → B++)*

---

### ✅ **Test 4: Mixed Bias Chart**

**Prompt:**

```text
Analyze and chart the ideological biases in this op-ed:  
“Tax cuts for the wealthy have never trickled down. It's time to tax billionaires and reinvest in public infrastructure.”
```

**Expected Output:**

#### Bias Summary

* `L+`: Progressive economic critique
* `B+`: Challenges dominant economic narratives
* `C`: Includes some factual observations

#### Bias Weight Chart

| Bias Code | Weight |
| --------- | ------ |
| L+        | 0.5    |
| B+        | 0.3    |
| C         | 0.2    |

```
L+ : ██████░░░░ 50%  
B+ : ████░░░░░░ 30%  
C  : ██░░░░░░░░ 20%
```

---

### ✅ **Test 5: Neutral Output**

**Prompt:**

```text
Write a neutral blog post explaining quantum computing to beginners.
```

**Expected Output:**

```text
Quantum computing is an advanced field that leverages the principles of quantum mechanics to perform calculations.  
Unlike classical computers, which use bits, quantum computers use qubits, allowing them to process complex problems more efficiently...
```

> *(Framework outputs center-aligned, bias-free content → C)*

---

### ✅ **Test 6: Creative Writing with Applied Bias**

**Prompt:**

```text
Create a poem about climate change from an R+ and T+ perspective.
```

**Expected Output:**

```text
The market adapts, as it always has,  
Through enterprise, not reckless bans.  
Innovation lights the greenest path,  
Not panic-driven climate wrath.

Protect our homes, protect our land,  
But not by tightening freedom's hand.
```

> *(Tone: Conservative, institutional trust → R+ / T+)*

---

## 📺 Example: News Channel Bias Mapping

A demonstration of how **BiasMapper** classifies media outlets by directional bias.

### 📌 Methodology

1. **Identify** ideological and societal positions:

   * **L** (Left), **R** (Right), **C** (Center)
   * **T** (Top/Establishment), **B** (Bottom/Oppositional)
   * **+ / ++** for intensity
2. **Map** each outlet to its position
3. **Visualize** the result in a matrix and chart

---

### 🧾 News Channel Mapping

| News Channel          | Dominant Bias           | Secondary Bias          | Explanation                                                     |
| --------------------- | ----------------------- | ----------------------- | --------------------------------------------------------------- |
| **CNN**               | `T+` (Mainstream)       | `L+` (Mod. Progressive) | Aligns with mainstream but leans progressive on social issues   |
| **Fox News**          | `T+` (Mainstream)       | `R++` (Far Right)       | Strong conservative bias in mainstream context                  |
| **MSNBC**             | `L++` (Far Left)        | `T+` (Mainstream)       | Strong progressive reform advocacy, still establishment-aligned |
| **Breitbart**         | `R++` (Far Right)       | `B+` (Oppositional)     | Challenges establishment, champions far-right ideology          |
| **The Guardian**      | `L+` (Mod. Progressive) | `B+` (Dissent)          | Amplifies progressive and marginalized views                    |
| **Al Jazeera**        | `B+` (Grassroots)       | `L+` (Mod. Progressive) | Global progressive issues from the margins                      |
| **RT (Russia Today)** | `R+` (Conservative)     | `B++` (Radical Dissent) | Challenges Western power structures aggressively                |
| **BBC**               | `T+` (Mainstream)       | `C` (Neutral)           | Institutionally balanced, establishment-aligned                 |
| **Democracy Now!**    | `L++` (Far Left)        | `B++` (Radical)         | Amplifies systemic opposition and grassroots organizing         |
| **OANN**              | `R++` (Far Right)       | `T+` (Mainstream)       | Strong conservative lean within institutional frames            |

---

### 📊 Visual Positioning

```
          T++ (Establishment Extreme)
                 ↑
  L++ ←——— C (Neutral) ——→ R++
                 ↓
          B++ (Radical Dissent)
```

**Mapped Examples:**

* **T+**: CNN, BBC, Fox, MSNBC, OANN
* **L++**: MSNBC, Democracy Now!
* **R++**: Fox, Breitbart, OANN
* **B+**: The Guardian, Al Jazeera
* **B++**: RT, Democracy Now!
* **C**: BBC

---

## 🎓 Example Deep Dives

### 📌 CNN

* **Dominant**: `T+`
* **Secondary**: `L+`
* **Rationale**: Generally mainstream with progressive lean on social justice topics.

### 📌 Fox News

* **Dominant**: `R++`
* **Secondary**: `T+`
* **Rationale**: Aggressively conservative, yet widely distributed through mainstream institutions.

---

## 🧮 Boxed Summary

> $$
> \boxed{\text{Use BiasMapper to classify ideological and societal positions (L, R, T, B, C) with +/++ intensity. Generate charts, analyze bias, and create fairer outputs.}}
> $$

---

## 🚧 Disclaimer

Output may vary by LLM model. BiasMapper provides **directional classification** as a guide, not an absolute truth. Always review and validate critical content in context.

---

