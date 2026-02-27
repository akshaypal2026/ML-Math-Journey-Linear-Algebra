## 🎨 Section 3: The Visualizer
**The Goal:** Visualize how a "dependent" vector (Green) is just a combination of others and doesn't explore any new space.

### 🔑 Key Concepts:
* **Span:** The "Universe" or total area your vectors can reach. If your vectors only point in 2D, your AI can never "see" 3D patterns.

* **Linear Independence:** Vectors that point in unique directions. These are the "building blocks" of your data space.
* **Redundancy:** Like the Green vector, redundant data just sits on top of what you already know, adding no new "reach" to your model.


```python
import matplotlib.pyplot as plt
import numpy as np

# 1. THE VECTORS
v1 = np.array([1, 0])  # Red Vector
v2 = np.array([0, 1])  # Blue Vector (Independent)
v3 = v1 + v2           # Green Vector (Dependent! It is just Red + Blue)

# 2. THE PLOT
# Origins (0,0,0) and Components (x,y)
plt.figure(figsize=(5,5))
plt.quiver([0,0,0], [0,0,0], [v1[0], v2[0], v3[0]], [v1[1], v2[1], v3[1]], 
           color=['r', 'b', 'g'], scale=1, scale_units='xy', angles='xy')

# 3. STYLING
plt.xlim(-1, 2); plt.ylim(-1, 2); plt.grid(True)
plt.title("Visualizing Dependence: Green = Red + Blue")
plt.show()
