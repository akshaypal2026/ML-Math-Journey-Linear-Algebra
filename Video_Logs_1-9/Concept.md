# 📊 Data Science Cheat Sheet: Linear Algebra Foundations
## (Videos 1–9: Structure, Cleaning, and Verification)

### 1. The Data Structure (Augmented Matrix)
* **The Math:** Stripping away variables (x, y, z) to leave just a grid of numbers.
* **DS Reality:** This is your **Feature Matrix**.
    * **Rows** = Individual observations (e.g., specific houses sold).
    * **Columns** = Features (e.g., Square Footage, Year Built, Price).
> **DS Note:** If your matrix isn't structured correctly, your model can't "read" the data.

### 2. The Cleaner (RREF - Reduced Row Echelon Form)
* **The Math:** Using Row Operations to get 1s on the diagonal and 0s elsewhere.
* **DS Reality:** This is **Feature Isolation**. It simplifies the "noise" so you can see the clear "signal" of how each feature independently impacts the result.

### 3. The Consistency Test (Solutions)
Before training a model, you check if the data is "telling the truth":
* **Unique Solution:** Clean data. Every input has one clear, logical output.
* **Infinite Solutions:** "Vague" data. You have **Free Variables** (gaps in info), and the AI has to guess.
* **No Solution:** "Corrupted" data. (e.g., A row says 0 = 5). This usually represents **Outliers** or data entry errors that will break your AI.

### 4. Linear Independence (The Redundancy Test)
* **The Math:** A set of vectors is independent if none can be made by combining the others.
* **DS Reality:** **Feature Selection.** If `Column A + Column B = Column C`, then Column C is "garbage" data. 
> **Action:** Delete Redundant Columns. It makes your model faster and prevents "confusion" (Multicollinearity).

### 5. Span (The "Universe")
* **The Math:** All possible points you can reach by scaling and adding your vectors.
* **DS Reality:** **Model Capacity.** If your data only spans a 2D plane, your AI is "blind" to the 3rd dimension. Your model can never predict something that exists outside its **Span**.

---

### 🏠 Case Study: The "Bangalore Apartment" Finder
You are predicting **Total Rent (₹)** based on three features:
1. **Bedrooms**
2. **Bathrooms**
3. **Half-Rooms** (Calculated as $0.5 \times$ Bedrooms)

| Bedrooms | Bathrooms | Half-Rooms | Total Rent (₹) |
| :--- | :--- | :--- | :--- |
| 2 | 2 | 1.0 | 60,000 |
| 4 | 3 | 2.0 | 110,000 |

**The Data Audit:**
* **Linear Dependence:** The "Half-Rooms" column is just $0.5 \times$ Bedrooms. It adds **zero** new info.
* **RREF Result:** When you "clean" this matrix, the Half-Rooms column will turn into zeros.
* **True Rank:** Even though you have 3 columns, your **Rank is 2**. You only have 2 "Useful" dimensions.

---

### 🏁 Final Summary for Video Logs
* **Pivots:** Your "MVP" features (the unique ones).
* **Rank:** Total number of useful, non-redundant columns.
* **Null Space:** The "dead weight" or useless info in your data.
* **Independence:** No "copy-cat" features allowed.

---
*Next Up: Video 10 — Linear Transformations (Moving Space!)*
