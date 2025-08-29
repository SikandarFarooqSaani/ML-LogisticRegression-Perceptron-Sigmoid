# Project 2: Perceptron + Sigmoid (Towards Logistic Regression)

This project builds on **Project 1: Perceptron from Scratch in Logistic Regression**.  
The main idea is to take the basic perceptron implementation and **replace the step function with a sigmoid function** to improve classification.  
This helps us move closer to the full implementation of **Logistic Regression from scratch**.

---

## 📚 Libraries Used
- **NumPy** → mathematical operations  
- **Matplotlib** → plotting and visualization  
- **Scikit-learn** → data generation and Logistic Regression for comparison  

---

## 🔎 Steps of the Project

### 1. Data Preparation
- Used the **same dataset** as Project 1:
  - Generated with `make_classification`
  - **100 samples**
  - **2 features**
  - **2 classes**
  - Random state = **41**
- Plotted the dataset → Verified that the classes are fairly **linearly separable**.

---

### 2. Perceptron Implementation (Recap from Project 1)
- Added **1 at index 0** in each feature row for intercept.  
- Initialized **weights** according to dataset dimensions.  
- Ran the loop for **1000 iterations**:
  - Randomly picked a row from dataset.  
  - Calculated prediction `ŷ = w · x`.  
  - Passed `ŷ` to a **step function**:  
    - If < 1 → output = 0  
    - If ≥ 1 → output = 1  
  - Updated weights:  
    ```
    weights = weights + learning_rate × (y_actual - y_hat) × row
    ```
- Returned:
  - `weights[0]` → **intercept**  
  - Remaining weights → **coefficients**  
- Calculated line parameters:
  - **Slope (m)** = `-a / b`  
  - **Intercept (c)** = `c / b`  
- Plotted the **Perceptron decision line**. ✅
- <img width="825" height="511" alt="download (1)" src="https://github.com/user-attachments/assets/18513703-1de0-4102-88c6-5f6f1680b021" />

---

### 3. Logistic Regression (Sklearn) Comparison
- Used `LogisticRegression` from `sklearn` on the same dataset.  
- Plotted the Logistic Regression line alongside the Perceptron line.  
- **Observation**:  
  - Perceptron line → Lies on the **boundary** of data.  
  - Logistic Regression line → Passes **through the middle**, better generalizing the separation.
  - <img width="825" height="511" alt="download (2)" src="https://github.com/user-attachments/assets/4c50fa8c-cffc-4672-b55a-ad2607315cd3" />

---

### 4. Sigmoid + Perceptron (New Concept in Project 2)
- Took the **same perceptron function** but **replaced the step function** with a **sigmoid function**.  
- The sigmoid function is defined as:  
- sigmoid(z) = 1 / (1 + e^(-z))

- Instead of producing hard outputs (0 or 1), sigmoid gives a **probability score** for each class.  
- Plotted the new line derived from the sigmoid-based perceptron.  
- Final plot included:
- <img width="825" height="511" alt="download (3)" src="https://github.com/user-attachments/assets/276fca90-31b3-45f3-877e-0bb4d2656049" />

- **Perceptron line (step function)**  
- **Sigmoid line**  
- **Logistic Regression line (from sklearn)**  


---

## 📊 Results & Comparison
- **Perceptron line**: Separates data but lies at the edge.  
- **Sigmoid line**: Slightly improved line compared to Perceptron.  
- **Logistic Regression line**: Balanced separation right in the middle.  

**Why difference?**  
- The Sigmoid-based perceptron is still not fully optimized because:
- We haven’t applied **Gradient Descent** to minimize the Logistic Regression **loss function**.
- The randomness in weight updates still affects the results.

---

## 🚀 Next Step
The next project will focus on:  
- Implementing **Logistic Regression from scratch**.  
- Using **Sigmoid + Gradient Descent** on the **Log Loss function**.  
- This will allow better optimization and more accurate decision boundaries.

---

## ✅ Learning Outcome
- Understood how replacing the step function with a sigmoid improves classification.  
- Observed that Sigmoid is a step towards **probabilistic classification**.  
- Learned why Logistic Regression is more stable → because it uses **gradient descent on log loss** instead of random updates.

---

## 📷 Visualizations
1. Scatter plot of dataset with **Perceptron line**  
2. Scatter plot comparing **Perceptron vs Logistic Regression line**  
3. Final plot with **Perceptron, Sigmoid, and Logistic Regression lines**  



---
