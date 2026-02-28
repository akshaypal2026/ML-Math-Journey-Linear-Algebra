# 🍿 The "Roommate Budget" Theory: x + y = 3

This repository explores the linear equation x + y = 3 using the "Roommate Rule." 

### 1. The House Law
Imagine two roommates, **x** and **y**, share an apartment. They have one unbreakable rule: The total number of snacks in the pantry must **always** be exactly **3**.

Mathematically: **x + y = 3**

### 2. The "Lazy Sunday" Strategy (Finding Intercepts)
When graphing, we usually look for the **Intercepts** first. This is basically assuming one roommate is doing absolutely nothing.

* **The y-intercept:** Roommate **x** is on vacation (x = 0). To keep the rule, roommate **y** has to buy all 3 snacks.
    * **Point:** (0, 3) — This is where the line hits the vertical y-axis.
* **The x-intercept:** Roommate **y** is taking a 24-hour nap (y = 0). Now **x** has to step up and buy all 3 snacks.
    * **Point:** (3, 0) — This is where the line hits the horizontal x-axis.

### 3. The "Teamwork" Reality
You don't *have* to be lazy. The roommates can share the load, but they must stay balanced to keep the total at 3:
* If **x** buys 1, **y** must buy 2 (1 + 2 = 3).
* If **x** buys 2, **y** must buy 1 (2 + 1 = 3).
* If **x** buys 1.5 snacks (don't ask me how), **y** buys 1.5 (1.5 + 1.5 = 3).
* **The Tragedy of (1, 1):** If both roommates only buy 1 snack, they only have 2 total. The "Equation Landlord" will evict them. The point (1, 1) is **NOT** on our line because 1 + 1 is not 3.

### 4. The Map (The Graph)
The "line" you see on a graph is just a visual map of every single possible way these two roommates can buy snacks without breaking the Law of 3.

---

## 🚀 The Visualizer (Python)

To see the "Snack Map" in action, run the following script.

```python
import matplotlib.pyplot as plt
import numpy as np

# Create the snack data
x = np.linspace(-1, 4, 100)
y = 3 - x  # Rearranged from x + y = 3

plt.figure(figsize=(8, 6))
plt.plot(x, y, label='The Snack Rule (x + y = 3)', color='#3498db', linewidth=3)

# Mark the "Lazy Sunday" Intercepts in red
plt.scatter([0, 3], [3, 0], color='#e74c3c', s=100, zorder=5) 
plt.text(-0.8, 3.2, 'Roommate X is away
