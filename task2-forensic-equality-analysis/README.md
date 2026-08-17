# Task 2: Forensic Technology - Gender Pay Equality Investigation

## Business Problem
Daikibo Industrials received internal complaints regarding potential gender inequality in compensation across company locations. Deloitte's Forensic Technology team calculated an **Equality Score** (-100 to +100, where 0 represents complete gender pay parity) for each job role across all factory sites.

---

## Technical Task
Classify each job role and factory combination into three distinct risk tiers based on the Equality Score metric to identify high-risk areas requiring immediate audit.

### Classification Rules & Logic
* **Fair:** Equality score within $\pm10$ ($-10 \le \text{Score} \le 10$).
* **Unfair:** Equality score between $\pm11$ and $\pm20$.
* **Highly Discriminative:** Equality score exceeding $\pm20$ ($\text{Score} < -20$ or $\text{Score} > 20$).

### Implementation (Excel IF / ABS Logic)
```excel
=IF(ABS(C2)<=10,"Fair",IF(ABS(C2)<=20,"Unfair","Highly Discriminative"))

---

## Summary Findings & Distribution

| Classification Tier | Score Range | Count of Roles / Percentage | Recommended Action |
| :--- | :--- | :--- | :--- |
| **Fair** | $-10 \le \text{Score} \le 10$ | [Insert Count / %] | Baseline monitoring |
| **Unfair** | $11 \le |\text{Score}| \le 20$ | [Insert Count / %] | Internal HR compensation audit |
| **Highly Discriminative** | $|\text{Score}| > 20$ | [Insert Count / %] | Immediate executive review & remediation |

### Key Executive Takeaway
* **Primary Concern:** [e.g., "X% of job roles across Daikibo factories were classified as Highly Discriminative."]
* **High-Risk Locations:** [Mention 1–2 factory locations that had the most Highly Discriminative scores].
