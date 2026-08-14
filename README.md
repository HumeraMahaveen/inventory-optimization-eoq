# Inventory Optimization — EOQ & Reorder Point Analysis

> A spreadsheet-based inventory optimization project for analyzing SKU-level demand, determining optimal order quantities, and setting replenishment points using EOQ, Safety Stock, and Reorder Point models.

---

## 📌 Project Overview

Inventory management requires balancing two competing problems:

- Ordering too frequently increases ordering costs.
- Holding too much inventory increases storage and carrying costs.
- Ordering too late can result in stockouts and service-level issues.

This project develops an **inventory optimization model for 25 SKUs** using Microsoft Excel.

The model calculates:

- Economic Order Quantity (EOQ)
- Safety Stock
- Reorder Point (ROP)
- Holding Cost per Unit per Year
- Annual Ordering + Holding Cost

The model is designed around an e-commerce / warehouse scenario and uses a **95% service-level assumption**.

---

## 🎯 Objectives

The main objectives of this project are to:

1. Determine the optimal order quantity for each SKU.
2. Calculate safety stock based on demand variability and lead time.
3. Identify when inventory should be replenished.
4. Estimate annual ordering and holding costs.
5. Support data-driven inventory management decisions.

---

## 🧮 Methodology

### 1. Economic Order Quantity (EOQ)

EOQ determines the approximate order quantity that balances ordering and inventory holding costs.

\[
EOQ = \sqrt{\frac{2DS}{H}}
\]

Where:

- `D` = Annual demand
- `S` = Ordering cost per order
- `H` = Annual holding cost per unit

### 2. Holding Cost

Annual holding cost per unit is calculated as:

\[
H = Unit\ Cost \times Holding\ Cost\ Rate
\]

### 3. Safety Stock

Safety stock provides a buffer against demand variability and lead-time uncertainty.

\[
Safety\ Stock = Z \times \sigma_d \times \sqrt{L}
\]

Where:

- `Z` = Service-level Z-score
- `σd` = Daily demand standard deviation
- `L` = Lead time in days

The model uses:

**Z = 1.65**, corresponding approximately to a 95% service-level assumption.

### 4. Reorder Point

The Reorder Point determines when a replenishment order should be placed.

\[
ROP = Daily\ Demand \times Lead\ Time + Safety\ Stock
\]

Daily demand is estimated as:

\[
Daily\ Demand = \frac{Annual\ Demand}{365}
\]

### 5. Annual Ordering + Holding Cost

The model estimates total annual inventory cost as:

\[
Total\ Cost =
\left(\frac{D}{EOQ}\right)S
+
\left(\frac{EOQ}{2}\right)H
\]

This helps evaluate the cost implications of different order quantities.

---

## 📊 Dataset

The workbook contains **25 simulated SKUs** across multiple product categories.

### Product Categories

- Apparel
- Grocery
- Home & Kitchen
- Books
- Footwear
- Toys
- Beauty
- Electronics

### Input Variables

Each SKU contains:

| Variable | Description |
|---|---|
| SKU | Unique product identifier |
| Category | Product category |
| Annual Demand | Expected annual unit demand |
| Ordering Cost | Cost incurred per purchase order |
| Unit Cost | Cost per inventory unit |
| Holding Cost % | Annual inventory carrying-cost percentage |
| Lead Time | Supplier/fulfillment lead time in days |
| Daily Demand Std Dev | Demand variability |

---

## 📈 Model Outputs

For each SKU, the model calculates:

| Output | Purpose |
|---|---|
| Holding Cost / Unit / Year | Annual cost of holding one unit |
| EOQ | Recommended order quantity |
| Safety Stock | Inventory buffer against variability |
| Reorder Point | Inventory level at which replenishment should begin |
| Annual Ordering + Holding Cost | Estimated annual inventory cost |

---

## 🔎 Sample Analysis

For example, SKU `FK-1001` has:

- Annual demand: **2,019 units**
- Ordering cost: **$483.70/order**
- Unit cost: **$672.64**
- Holding cost: **17%**
- Lead time: **3 days**
- EOQ: **131 units**
- Safety stock: **5 units**
- Reorder point: **22 units**

This means the model recommends placing an order of approximately **131 units** when inventory reaches approximately **22 units**, based on the model assumptions.

---

## 📊 Summary of Current Model

The current workbook analyzes:

| Metric | Result |
|---|---:|
| SKUs analyzed | 25 |
| Total annual demand | 244,925 units |
| Average EOQ | 178 units |
| Average Reorder Point | 269 units |
| Average Safety Stock | 34 units |
| Total estimated annual ordering + holding cost | $1,013,122.60 |
| Service-level assumption | 95% |

> Results are based on the simulated dataset included in this project.

---

## 🖥️ Excel Workbook

The main workbook contains an **Inventory Analysis** sheet with:

- Editable inventory inputs
- Formula-driven calculations
- SKU-level EOQ calculations
- Safety-stock calculations
- Reorder-point calculations
- Annual inventory-cost calculations
- Summary metrics
- EOQ visualization

The model is designed so that changing inputs such as demand, ordering cost, holding cost, lead time, or the service-level Z-score automatically updates the calculations.

---

## 🛠️ Tools & Technologies

- **Microsoft Excel**
- Excel formulas
- Inventory Management Models
- Quantitative Analysis
- Data Analysis
- EOQ Model
- Safety Stock Model
- Reorder Point Model

---

## 💼 Business Application

This type of analysis can support warehouse and supply-chain decisions such as:

- When to replenish inventory
- How much inventory to order
- How much safety stock to maintain
- How demand variability affects inventory levels
- How ordering and holding costs affect inventory decisions

The same concepts can be applied to e-commerce fulfillment, retail warehouses, distribution centers, and other inventory-driven operations.

---

## 📂 Project Structure

```text
inventory-optimization-eoq/
│
├── README.md
│
└── Inventory_EOQ_Reorder_Point_Analysis.xlsx
