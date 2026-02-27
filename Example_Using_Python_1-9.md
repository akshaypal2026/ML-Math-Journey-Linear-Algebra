# ==========================================
# 📂 MASTER LOG: VIDEOS 1–9 (Python + Math)
# ==========================================

import numpy as np
import sympy as sp
import matplotlib.pyplot as plt

# ---------------------------------------------------------
# 🏗️ SECTION 1: THE SOLVER (Finding Feature Weights)
# ---------------------------------------------------------
# Concept: We use Row Reduction to find the exact "Weight" 
# of features like Bedrooms and Bathrooms.

# Features: [Bedrooms, Bathrooms] 
# Apt 1: 2 Bed, 1 Bath | Apt 2: 1 Bed, 2 Bath
A = np.array([[2, 1], 
              [1, 2]])

# Target: Prices (₹50L and ₹40L)
B = np.array([50, 40])

# np.linalg.solve: Finds the Unique Solution (Intersection point)
solution = np.linalg.solve(A, B)

print("--- SECTION 1: THE SOLVER ---")
print(f"Result: Price per Bedroom is ₹{solution[0]}L")
print(f"Result: Price per Bathroom is ₹{solution[1]}L")


# ---------------------------------------------------------
# 🔍 SECTION 2: THE AUDITOR (Checking for Redundancy)
# ---------------------------------------------------------
# Concept: "Rank" tells us how many useful columns we have.
# If a column is just a copy or calculation of another, Rank decreases.

# Data: Area, Rooms, and (Area * 2) <- Redundant!
matrix = np.array([[1000, 2, 2000],
                   [1500, 3, 3000],
                   [2000, 4, 4000]])

rank = np.linalg.matrix_rank(matrix)
num_cols = matrix.shape[1]

print("\n--- SECTION 2: THE AUDITOR ---")
print(f"Total Columns: {num_cols}")
print(f"Useful Features (Rank): {rank}")

if rank < num_cols:
    print("⚠️ Verdict: Redundant data detected! Delete 'copy-cat' columns.")


# ---------------------------------------------------------
# 🎨 SECTION 3: THE VISUALIZER (Linear Dependence)
# ---------------------------------------------------------
# Concept: A "Dependent" vector (Green) doesn't add a new 
# direction; it just lands where Red + Blue already go.

# Define Vectors
v1 = np.array([1, 0])  # Red
v2 = np.array([0, 1])  # Blue
v3 = v1 + v2           # Green (Dependent on Red and Blue)

# Origins for the arrows
origins_x, origins_y = [0, 0, 0], [0, 0, 0]
veccs_x, veccs_y = [v1[0], v2[0], v3[0]], [v1[1], v2[1], v3[1]]

plt.figure(figsize=(5,5))
plt.quiver(origins_x, origins_y, veccs_x, veccs_y, 
           color=['r', 'b', 'g'], scale=1, scale_units='xy', angles='xy')

plt.xlim(-1, 2); plt.ylim(-1, 2); plt.grid(True, linestyle='--')
plt.axhline(0, color='black', linewidth=1); plt.axvline(0, color='black', linewidth=1)
plt.title("Visualizing Dependence: Green = Red + Blue")
plt.show()

# ==========================================
# 🏁 KEY TERMS FOR YOUR NOTEBOOK:
# 1. Unique Solution: Data is perfect; every input has one output.
# 2. Rank: The number of "true" dimensions in your data.
# 3. Span: The boundaries of what your AI can actually see.
# 4. Independence: No "copy-cat" columns allowed!
# ==========================================
