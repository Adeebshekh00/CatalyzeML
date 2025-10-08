# ⚡ Machine Learning-Based Analysis of Electro-Catalyst For Hydrogen Evolution Reaction (HER)

### 📘 Overview
This project explores the use of **Machine Learning (ML)** techniques to identify and predict the most efficient, economically viable, and sustainable **catalyst families** for the **Hydrogen Evolution Reaction (HER)** — a key process in clean hydrogen production via water electrolysis.

By combining theoretical electrochemistry with data-driven modeling, this work aims to bridge the gap between **experimental catalyst design** and **predictive computational insights**.

---

## 🧠 Motivation — Why We Chose This Topic
- The **Hydrogen Evolution Reaction (HER)** plays a crucial role in renewable energy systems, driving the production of **green hydrogen**.  
- Through extensive literature review, we found that **most HER studies focus purely on experimental catalyst optimization**, leaving a gap in **data-driven, predictive approaches**.  
- This project addresses that gap by applying **machine learning models** to identify **high-performance, low-cost, and sustainable catalysts** based on electrochemical parameters.  
- By combining **experimental insights** with **computational modeling**, we aimed to identify **the most efficient and economically viable catalyst families** for HER.  
- Our objective was to develop a **predictive framework** that relates key electrochemical parameters to HER efficiency, helping researchers and engineers make informed design choices.  
- The project aligns with the broader goal of **advancing green hydrogen technologies**, demonstrating how **AI/ML can bridge experimental chemistry and sustainable energy innovation**.

---

## ⚗️ Theoretical Background

The **Hydrogen Evolution Reaction (HER)** is one of the two half-cell reactions in water electrolysis, occurring at the **cathode** and responsible for generating molecular hydrogen (H₂).  
Depending on the **electrolyte medium**, HER proceeds through slightly different pathways but follows the same fundamental principle: **electron transfer to protons or water molecules to form H₂ gas**.

---

### 🧪 **1. Overall HER Reaction**

#### ⚫ In Acidic Medium:
$2H^+ + 2e^- \rightarrow H_2$

#### ⚫ In Alkaline Medium:
$2H_2O + 2e^- \rightarrow H_2 + 2OH^-$

In both cases, two electrons are required to generate one molecule of hydrogen.

---

### ⚙️ **2. Elementary Reaction Steps**

HER typically occurs through **three key steps**, known as the **Volmer–Heyrovsky–Tafel mechanism**.  
Each catalyst’s performance depends on which step is **rate-determining** and how easily it proceeds.

#### ⚫ (a) Volmer Step — Electrochemical Adsorption  
The **first step**, where hydrogen ions (H⁺) or water molecules are reduced to adsorbed hydrogen atoms (H*) on the catalyst surface.  

- *In acidic medium:*  
  $H^+ + e^- \rightarrow H^*$

- *In alkaline medium:*  
  $H_2O + e^- \rightarrow H^* + OH^-$ 

This step depends strongly on the catalyst’s ability to **adsorb hydrogen**.

---

#### ⚫ (b) Heyrovsky Step — Electrochemical Desorption  
An adsorbed hydrogen atom combines with a proton (or another water molecule) and an electron to form hydrogen gas:  

- *In acidic medium:*  
  $H^* + H^+ + e^- \rightarrow H_2$

- *In alkaline medium:*  
  $H^* + H_2O + e^- \rightarrow H_2 + OH^-$

This step involves both **charge transfer and desorption of hydrogen** — it’s often dominant in alkaline media.

---

#### ⚫ (c) Tafel Step — Chemical Recombination  
Two adsorbed hydrogen atoms combine directly on the catalyst surface to produce H₂ gas:

$2H^* \rightarrow H_2$

This step doesn’t require additional electrons — it’s a **surface reaction**, typically favored on catalysts with high hydrogen coverage.

---

### ⚡ **3. Summary**
The HER mechanism is a balance between:
- **Adsorption strength** of hydrogen on the surface (Volmer step),  
- **Ease of electron/proton transfer** (Heyrovsky step), and  
- **Desorption rate** of hydrogen gas (Tafel step).  

An ideal catalyst facilitates all three steps efficiently — a principle captured beautifully by the **Volcano Plot** relationship between **M–H bond strength** and **exchange current density**.

---

## 💾 Dataset Description
Two datasets were prepared and used for model training and validation:

1. **Synthetic (Physics-Guided) Dataset**
   - Generated using physically consistent trends derived from HER literature.
   - Parameters include *pH, temperature, Tafel slope, ECSA, exchange current density, morphology score, and overpotential*.

2. **Real Experimental Dataset**
   - Extracted from published research papers and supporting information files.
   - Contains real catalyst data (phosphides, sulfides, carbides, and noble metals) with reported overpotentials and conditions.

---

## 🧮 Machine Learning Models Used
To predict catalyst performance and classify optimal catalyst families, the following models were implemented:

- 🌲 **Random Forest Classifier** – Robust against overfitting, strong interpretability  
- 🌾 **Gradient Boosting Classifier** – High accuracy through ensemble learning  
- ⚡ **XGBoost Classifier** – Optimized gradient boosting with better generalization  
- 🌳 **Decision Tree Classifier** – Simple, interpretable baseline model  

**Why these models?**  
They effectively capture **non-linear interactions** among parameters like pH, morphology, and ECSA, and provide **feature importance rankings** to interpret the scientific significance of each feature.

---

## 🧩 Key Findings
- The **phosphide family with molybdenum as the metal component** && **sulphide family with iron as the metal component** consistently ranked highest across all models, making it the **best-fit catalyst** for HER based on aggregated predictions.  
- **Important features** influencing HER activity include:
  - Morphology factors  
  - Electrochemical surface area (ECSA)  
  - Electrolyte pH  
  - Exchange current density  
- The models demonstrated high confidence and consistency in identifying sustainable, non-noble metal catalysts with strong performance potential.

---

## 🚀 Future Scope
- **Deep Feature Exploration:**  
  Investigate the most influential parameters (morphology, ECSA, pH, current density) for molybdenum phosphide using new experimental and literature data.

- **Enhanced ML Modeling:**  
  Build predictive regression models to optimize HER performance parameters under variable conditions.

- **Streamlit-Based UI:**  
  Develop an interactive web interface allowing users to input operating conditions (e.g., pH, temperature, catalyst type) and visualize predicted HER performance and recommendations.

- **Smart Suggestion System:**  
  Integrate data-driven guidance within the UI to recommend optimal parameter ranges and highlight potential inefficiencies.

---

## 🧪 Tools & Technologies
- **Python** (Pandas, NumPy, Scikit-learn, ML-Algorithms, Matplotlib, Seaborn)
- **Jupyter Notebook / Google Colab**
- **Streamlit** for UI deployment
- **Research data extraction** from literature (ACS, RSC, Electrochimica Acta, etc.)
---

## 📊 Visual Insight — HER Volcano Plot
The relationship between **exchange current density (log j₀)** and **M–H bond strength** follows a **volcano trend**, illustrating the **Sabatier principle** — the catalyst must bind hydrogen neither too weakly nor too strongly for optimal activity.  
This principle supports why **Mo-based phosphides** perform exceptionally well — they strike a near-optimal balance between adsorption and desorption energetics.

---

## 📚 References
1. Feidenhans’l, A. A. *et al.* “Precious Metal-Free Hydrogen Evolution Catalyst Design and Application,” *Electrochimica Acta*, 2023.  
2. Jaramillo, T. F. *et al.* “Active Sites and Hydrogen Binding Energy in HER Catalysts,” *Science*, 2007.  
3. Open Catalyst Project, *OC20 Dataset for Catalysis ML Research*, 2020.  
4. Standard electrochemical HER studies — ACS Energy Letters, RSC Advances, etc.

---
