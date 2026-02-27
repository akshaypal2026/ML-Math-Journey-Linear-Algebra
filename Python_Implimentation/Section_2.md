## 🔍 Section 2: The Auditor
**The Goal:** Check if your dataset has "copy-cat" columns (Redundant Data) that provide zero new information to your model.

### 🔑 Key Concepts:
* **Rank:** The number of "true" dimensions in your data. It tells you how many columns actually matter.

* **Linear Dependence:** When one column is just a calculation of another. It adds "noise" and makes models slower without adding value.


```python
import numpy as np

# 1. THE DATA
# Feature 1: Area | Feature 2: Rooms | Feature 3: Area x 2 (Redundant!)
matrix = np.array([[1000, 2, 2000],
                   [1500, 3, 3000],
                   [2000, 4, 4000]])

# 2. THE AUDIT
# "Rank" counts the number of useful columns (Pivots)
rank = np.linalg.matrix_rank(matrix)
num_cols = matrix.shape[1]

print(f"Total Columns: {num_cols}")         # Result: 3
print(f"Useful Features (Rank): {rank}")    # Result: 2

# 3. THE VERDICT
if rank < num_cols:
    print("⚠️ Redundant data detected! One column is just a copy-cat.")
