# 🛡️ ARX Dataset Anonymization — Utility & Risk Analysis

Project for **Security and Privacy (2024/2025)** using the **ARX Data Anonymization Tool** to anonymize a dataset and study the **privacy–utility trade-off**. We assess **re-identification risk** under ARX attacker models and compare **k-anonymity** vs **distinct ℓ-diversity**, including a small sensitivity study (suppression limit, coding model, weights).

**Authors:** Francisca Cerqueira · Iara Ferreira · Rodrigo Simões (PL01_9) 

---

## What we did
- **Attributes:** most variables treated as **QIDs**; `salary-class` used as **SA** for ℓ-diversity. 
- **Baseline risk (original):** very high — ~**93%** records at risk, **100%** highest risk, ~**80%** success rate; sample uniques **69.33%**, population uniques **4.17%** (Pitman). 

## Models & main results
- **k-anonymity (k=5, Global + Optimal search):** records at risk **0%**, highest risk **20%**, success rate **3.52%**. 
  Utility: generalization **56.35%**, granularity **69.09%**, non-uniform entropy **38.88%**, discernibility **85.59%**.   
- **distinct ℓ-diversity (ℓ=2, SA=`salary-class`):** highest risk **50%**, success rate ~**2–3%** (Prosecutor 3.47%, Journalist/Marketer 2.28%).  
  Utility: generalization **56.46%**, granularity **65.04%**, non-uniform entropy **35.97%**, discernibility **83.56%**.  

## Sensitivity highlights
- **Suppression limit:** tested **2.5–100%**; metrics mostly plateau after **20%** → good trade-off. 
- **Global vs Local recoding:** Local improves utility but increases risk (k=5: **3.52%→12.42%**, ℓ=2: **3.47%→16.81%**) → we kept **Global**.
- **Weights:** reduced success rate (k=5: **3.52%→2.26%**, ℓ=2: **3.47%→2.62%**).  

## Final submitted setup
**k-anonymity (k=5)** with **20% suppression**, **Global transformation**, and **attribute weights** (best overall privacy–utility balance).


## Reproduce
Open ARX → **File → Open Project** → `arx-project/PL01_9.zip`, then check **Analyze Risk** and **Analyze Utility**.
