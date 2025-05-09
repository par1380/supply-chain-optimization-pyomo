# Supply Chain Optimization in Python using Pyomo

This project models and solves a 3-level supply chain optimization problem using [Pyomo](http://www.pyomo.org/) in Python.  
The goal is to minimize total cost over a 3-month period while meeting customer demands via optimal transportation and inventory decisions.

---

## 📦 Problem Structure

### 📍 Components:
- **Factories (i)**: P1, P2
- **Warehouses (j)**: W1, W2, W3
- **Customers (k)**: C1, C2, C3, C4
- **Time Periods (t)**: Months 1 to 3

### 🧮 Decision Variables:
- `F[i,j,t]`: Number of pallets transported from factory `i` to warehouse `j` at month `t`
- `W[j,k,t]`: Number of pallets shipped from warehouse `j` to customer `k` at month `t`
- `I[j,t]`: Inventory held at warehouse `j` at the end of month `t`
- `S[k,t]`: Shortage (unmet demand) for customer `k` in month `t`

---

## 🎯 Objective

Minimize total cost:
- 📦 Factory → Warehouse transport
- 🚚 Warehouse → Customer transport
- 🏬 Inventory holding cost
- ⚠️ Shortage penalty cost

The objective function is modeled as:

Total Cost = Transportation (F, W) + Inventory Holding (I) + Shortage Penalty (S)

---

## 🧾 Constraints

- ✅ **Warehouse Capacity**: Inventory cannot exceed storage limits  
- ✅ **Customer Demand**: Either fulfilled through shipment or counted as shortage  
- ✅ **Production Capacity**: Each factory has a max monthly capacity  
- ✅ **Inventory Balance**: Tracks incoming/outgoing stock per warehouse per month

---

## 🧠 Technologies Used

- Python 3  
- [Pyomo](https://pyomo.readthedocs.io/en/stable/)  
- GLPK Solver (recommended, install via `conda` or `apt`)

---

## 💻 How to Run

1. Clone the repo:

git clone https://github.com/par1380/supply-chain-optimization-pyomo
cd supply-chain-optimization-pyomo

2.Install dependencies:

pip install pyomo

🔹 If you want to use GLPK solver:

On Windows:
Install GLPK via conda or download binaries

On Ubuntu/Linux
sudo apt install glpk-utils

3.Run the model
python main_model.py


🤝 Author
Developed by [Parsa Fadaie]














