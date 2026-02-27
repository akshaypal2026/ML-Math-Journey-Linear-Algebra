# 📂 Video Log: Linear Algebra Mastery (Videos 1–9)
> **Goal:** Understanding Data Structure, Integrity, and Visualization through Python.

---

## 🏗️ Section 1: The Solver (Finding Model Weights)
**The Concept:** Finding the "Unique Solution." In Data Science, we use this to find the "Weights"—exactly how much each feature (like a Bedroom) contributes to a result (like Price).

```python
import numpy as np

# A = Feature Matrix (Apt 1: 2 Bed, 1 Bath | Apt 2: 1 Bed, 2 Bath)
A = np.array([[2, 1], 
              [1, 2]])

# B = Target Vector (Apt 1 costs ₹50L | Apt 2 costs ₹40L)
B = np.array([50, 40])

# Solve: Performs automated Row Reduction (RREF)
solution = np.linalg.solve(A, B)

print("--- SECTION 1: THE SOLVER ---")
print(f"Price per Bedroom: ₹{solution[0]}L")  # The Weight of Feature 1
print(f"Price per Bathroom: ₹{solution[1]}L") # The Weight of Feature 2

Important Term:

Unique Solution: Every input has a clear, logical answer. If the lines didn't intersect, your data would be corrupted.

