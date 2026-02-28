# 📐 Linear Algebra: What is a Vector?
*Notes based on Dr. Trefor Bazett's Linear Algebra Series (Video 11)*

## 📌 Core Concept
If Gaussian elimination is the "engine," **vectors** are the "fuel." A vector is a mathematical object that represents a **Magnitude** (length) and a **Direction**.

---

## 🎨 Two Ways to Visualize a Vector

### **1. The Geometric View (The Arrow)**
* **The Picture:** An arrow starting from the origin $(0,0)$ and pointing to a coordinate $(x, y)$.
* **Vector Addition:** Uses the **Tip-to-Tail** method. Place the start of the second vector at the end of the first. The "shortcut" from the start to the final end is your result.

* **Scalar Multiplication:** Multiplying a vector by a number (a "scalar") stretches or shrinks it. Multiplying by a negative number flips the arrow's direction.


### **2. The Algebraic View (The List)**
* **The Picture:** A vector is simply a column of numbers: $\begin{bmatrix} x \\ y \end{bmatrix}$.
* **Addition:** You simply add the corresponding components (top + top, bottom + bottom).
* **Scalar Multiplication:** You multiply every number in the list by that scalar.

---

## 🚀 Data Science Implementation: The "Why"

In Data Science, we treat every row in a dataset as a **Vector**.

1.  **Feature Vectors:** If you are predicting house prices:
    * $x_1$ = Square footage
    * $x_2$ = Number of bedrooms
    * $x_3$ = Year built
    * Each house is a vector in **3D space**.
2.  **Distance & Similarity:** We use vectors to find how "close" two data points are. For example, Netflix recommends movies by finding a **Movie Vector** that points in a similar direction to your **User Preference Vector**.
3.  **Scaling (Normalization):** When we rescale data (e.g., making all values between $0$ and $1$), we are performing **Scalar Multiplication** on our entire feature set.

---

## 🐍 Python Implementation (NumPy)

Standard Python lists don't follow math rules (adding two lists just joins them). We use **NumPy** to treat them as true mathematical vectors.

```python
import numpy as np

# 1. Define Vectors
v = np.array([1, 2])
u = np.array([3, -1])

# 2. Vector Addition (Tip-to-Tail Logic)
# Algebraic Result: [1+3, 2-1] = [4, 1]
w = v + u
print(f"Addition Result: {w}")

# 3. Scalar Multiplication (Stretching/Shrinking)
# Result: [2*1, 2*2] = [2, 4]
scaled_v = 2 * v
print(f"Scaled Vector: {scaled_v}")

# 4. Magnitude (Finding the 'Length' of the arrow)
length = np.linalg.norm(v)
print(f"Magnitude of v: {length:.2f}")
