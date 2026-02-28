# 📐 Linear Algebra: What is a Vector?
*Notes based on Dr. Trefor Bazett's Linear Algebra Series (Video 11)*

---

## 📌 Core Concept

If Gaussian elimination is the **engine**, then **vectors are the fuel** of linear algebra.

A **vector** is something that has:

- ✅ Magnitude (length)  
- ✅ Direction  

In simple words:

> A vector tells you how to move.

Example:

(2, 3)

Means:
- Move 2 units right
- Move 3 units up

---

# 🎨 Two Ways to Think About a Vector

---

## 1️⃣ The Geometric View (Arrow Picture)

### 🖼 What It Looks Like

A vector is an arrow starting at the origin (0,0) and pointing to (x, y).

Example:

(3, 1)

Draw arrow from (0,0) → (3,1)

---

### ➕ Vector Addition (Tip-to-Tail Method)

If:

v = (1,2)  
u = (3,-1)

Add component-wise:

(1,2) + (3,-1) = (4,1)

Geometric idea:
1. Draw vector v
2. From its tip, draw vector u
3. The shortcut from start to final point is v + u

---

### ✖ Scalar Multiplication

A scalar is just a number.

Example:

2(1,2) = (2,4)

What happens visually?

- Multiply by 2 → arrow becomes twice as long  
- Multiply by 0.5 → arrow becomes shorter  
- Multiply by -1 → arrow flips direction  

---

## 2️⃣ The Algebraic View (List of Numbers)

A vector can also be written as a column:

[x  
 y]

Example:

[1  
 2]

---

### ➕ Addition Rule

Add matching positions:

[1  
 2]
+
[3  
 -1]
=
[4  
 1]

Top + Top  
Bottom + Bottom  

---

### ✖ Scalar Rule

Multiply every number:

3 × [1  
      2]

=

[3  
 6]

---

# 📏 Magnitude (Length of a Vector)

Formula:

||v|| = √(x² + y²)

Example:

v = (3,4)

||v|| = √(3² + 4²)  
      = √(9 + 16)  
      = √25  
      = 5

This comes from the Pythagorean theorem.

---

# 🚀 Data Science Implementation — Why This Matters

In Data Science:

👉 Every row in a dataset is a vector.

Example: Predicting house prices

x = [Size, Bedrooms, Age]

A house:

[1200, 3, 10]

This is a point in 3D space.

---

## 🧠 Where Vectors Are Used

1️⃣ Feature Vectors  
Each data row = vector of features.

2️⃣ Distance & Similarity  
Used in:
- Recommendation systems
- Clustering
- Similarity search

3️⃣ Scaling (Normalization)  
If a feature is too large:

0.01 × Salary

This is scalar multiplication.

---

# 🐍 Python Implementation (Using NumPy)

Normal Python lists do NOT behave like math vectors:

[1,2] + [3,4]
# Output: [1,2,3,4]  ❌

So we use NumPy.

```python
import numpy as np

# 1️⃣ Define vectors
v = np.array([1, 2])
u = np.array([3, -1])

# 2️⃣ Vector Addition
w = v + u
print("Addition Result:", w)
# [4 1]

# 3️⃣ Scalar Multiplication
scaled_v = 2 * v
print("Scaled Vector:", scaled_v)
# [2 4]

# 4️⃣ Magnitude (Length)
length = np.linalg.norm(v)
print("Magnitude of v:", round(length, 2))
```

---

# 🎯 Final Understanding

- A vector is a movement.
- Addition = combine movements.
- Scalar multiplication = stretch or shrink movement.
- In data science, vectors represent data points.

Everything else in linear algebra builds on this.
