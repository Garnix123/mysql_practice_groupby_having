# 🌿 Lucky Shrub – SQL `GROUP BY` & `HAVING` Practice

## 📌 Overview
This project demonstrates the use of SQL **GROUP BY** and **HAVING** clauses with the fictional **Lucky Shrub** garden design firm database.

---

## 🖼 Sample Table Data

| OrderID | Department         | OrderDate  | OrderQty | OrderTotal |
|---------|-------------------|------------|----------|------------|
| 1       | Lawn Care         | 2022-05-05 | 12       | 500        |
| 2       | Decking           | 2022-05-22 | 150      | 1450       |
| 3       | Compost & Stones  | 2022-05-27 | 20       | 780        |
| 4       | Trees & Shrubs    | 2022-06-01 | 15       | 400        |
| 5       | Garden Decor      | 2022-06-10 | 2        | 1250       |
| ...     | ...               | ...        | ...      | ...        |

---

## 🎯 Tasks & Solutions

```sql
-- Task 1 – Group orders by date
SELECT OrderDate
FROM Orders
GROUP BY OrderDate;

-- Task 2 – Count orders per date
SELECT OrderDate, COUNT(OrderDate) AS OrderCount
FROM Orders
GROUP BY OrderDate;

-- Task 3 – Total quantities by department
SELECT Department, SUM(OrderQty) AS TotalQuantity
FROM Orders
GROUP BY Department;

-- Task 4 – Orders between 1st and 30th June 2022
-- Using WHERE before GROUP BY
SELECT OrderDate, COUNT(OrderID) AS OrdersCount
FROM Orders
WHERE OrderDate BETWEEN '2022-06-01' AND '2022-06-30'
GROUP BY OrderDate;

-- Alternative: Using HAVING after GROUP BY
SELECT OrderDate, COUNT(OrderID) AS OrdersCount
FROM Orders
GROUP BY OrderDate
HAVING OrderDate BETWEEN '2022-06-01' AND '2022-06-30';
🗂 Schema Diagram
+-----------------------------+
|          Orders             |
+-----------------------------+
| OrderID (PK)                |
| Department                  |
| OrderDate                   |
| OrderQty                    |
| OrderTotal                  |
+-----------------------------+
