# 🌿 Lucky Shrub – SQL `GROUP BY` & `HAVING` Practice

## 📌 Overview
This project demonstrates the use of SQL **GROUP BY** and **HAVING** clauses with the fictional **Lucky Shrub** garden design firm database.  
The objective is to group and filter aggregated data to gain insights from the Orders table.

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

### **Task 1 – Group orders by date**
```sql
SELECT OrderDate
FROM Orders
GROUP BY OrderDate;
Purpose: Lists each unique order date once.

Task 2 – Count orders per date
sql
Zkopírovat
Upravit
SELECT OrderDate, COUNT(OrderDate) AS OrderCount
FROM Orders
GROUP BY OrderDate;
Purpose: Shows how many orders were placed on each date.

Task 3 – Total quantities by department
sql
Zkopírovat
Upravit
SELECT Department, SUM(OrderQty) AS TotalQuantity
FROM Orders
GROUP BY Department;
Purpose: Displays total quantity ordered for each department.

Task 4 – Orders between 1st and 30th June 2022
sql
Zkopírovat
Upravit
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
