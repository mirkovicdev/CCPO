# Cardinality-Constrained Portfolio Optimization

This project explores **portfolio optimization under cardinality constraints**, where the number of assets selected in a portfolio is explicitly limited. Using integer programming, the project demonstrates how adding a cardinality constraint transforms a convex Markowitz optimization problem into a **combinatorial, non-convex challenge**—motivating the need for advanced solvers and quantum-inspired approaches.

---

## 🧠 What It Does

Given:
- A covariance matrix of asset returns $$\Sigma$$
- A vector of expected returns $$\mu$$
- A target expected return $$r^*$$
- A cardinality limit $$K$$ (max number of non-zero assets)

The optimizer solves:

$$
\min_w \quad w^T \Sigma w \quad \text{subject to:}
$$

- $\sum w_i = 1$ (fully invested)
- $\mu^T w \geq r^*$ (target return)
- $w_i \leq z_i, \quad z_i \in \{0, 1\}$ (selection constraint)
- $\sum z_i \leq K$ (cardinality constraint)
- $w_i \geq 0$ (long-only)

---

## 🔍 Features

- ✅ Solves the **cardinality-constrained minimum-variance** problem
- ✅ Compares with the unconstrained Markowitz solution
- ✅ Uses `mip` for mixed-integer quadratic programming
- ✅ Visualizes how limiting asset count affects portfolio composition and performance
- ✅ Prepares groundwork for future QUBO or quantum annealing implementations

---

## 📊 Visualization

- Efficient frontier with vs. without cardinality constraint
- Portfolio weights vs. cardinality limit
- Risk-return tradeoff curves and asset sparsity plots

---

## 📦 Requirements

- Python 3.x
- NumPy
- Matplotlib
- `mip` (Mixed Integer Programming)

Install dependencies:

```bash
pip install numpy matplotlib mip
