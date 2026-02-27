# 📂 Video Log: Linear Algebra Mastery (Videos 1–9)
> **Status:** Foundations Complete | **Focus:** Data Integrity & Python Implementation

---

## 🏗️ Section 1: The Solver
**The Goal:** Find the exact price for one bedroom and one bathroom based on two apartment examples.
**Key Concepts:** 
Unique Solution: Your data is clean; the lines intersect at one perfect point.
Weights: The results (20 and 10). This is the "logic" the AI uses to predict prices for new houses.



```python
import numpy as np

# 1. THE DATA: [Bedrooms, Bathrooms]
A = np.array([[2, 1],   # Apt 1: 2 Bed, 1 Bath
              [1, 2]])  # Apt 2: 1 Bed, 2 Bath

# 2. THE PRICES: [Total Rent in Lakhs]
B = np.array([50, 40])

# 3. THE MATH: Automated Row Reduction (RREF)
# Finds the weights (prices) for each individual feature
solution = np.linalg.solve(A, B)

print(f"Price per Bedroom:  ₹{solution[0]}L") # Result: 20
print(f"Price per Bathroom: ₹{solution[1]}L") # Result: 10

🔑 Key Concepts:
Unique Solution: Your data is clean; the lines intersect at one perfect point.

Weights: The results (20 and 10). This is the "logic" the AI uses to predict prices for new houses.
