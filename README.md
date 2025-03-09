# dbeaver-sql-data-analysis


Sure! Below is a breakdown of each query with **explanations, use cases, and example tables**.

---

## **1. Retrieve All Data**
### **Query:**
```sql
SELECT * FROM dataset_1;
```
### **Explanation:**
- Selects **all columns** and **all rows** from `dataset_1`.

### **Example Table (`dataset_1`)**:
| id | destination | weather | temperature | passanger | coupon | occupation |
|----|------------|---------|------------|-----------|--------|------------|
| 1  | Home       | Sunny   | 30         | Alone     | 5      | Student    |
| 2  | Office     | Cloudy  | 22         | Group     | 10     | Engineer   |
| 3  | Park       | Rainy   | 18         | Alone     | 3      | Manager    |

---

## **2. Select Specific Columns**
### **Query:**
```sql
SELECT weather, temperature FROM dataset_1;
```
### **Explanation:**
- Retrieves **only the `weather` and `temperature`** columns.

### **Result Set:**
| weather | temperature |
|---------|------------|
| Sunny   | 30         |
| Cloudy  | 22         |
| Rainy   | 18         |

---

## **3. Limit the Number of Rows**
### **Query:**
```sql
SELECT * FROM dataset_1 LIMIT 10;
```
### **Explanation:**
- Retrieves **only the first 10 rows** from `dataset_1`.

### **Use Case:**
- Useful when working with **large datasets** to fetch a sample.

---

## **4. Select Unique Values (`DISTINCT`)**
### **Query:**
```sql
SELECT DISTINCT passanger FROM dataset_1;
```
### **Explanation:**
- Retrieves **unique values** from the `passanger` column.

### **Result Set:**
| passanger |
|----------|
| Alone    |
| Group    |

---

## **5. Filter Rows (`WHERE` Clause)**
### **Query:**
```sql
SELECT * FROM dataset_1 WHERE destination = 'Home';
```
### **Explanation:**
- Retrieves **only the rows where `destination` is 'Home'**.

### **Result Set:**
| id | destination | weather | temperature | passanger | coupon | occupation |
|----|------------|---------|------------|-----------|--------|------------|
| 1  | Home       | Sunny   | 30         | Alone     | 5      | Student    |

---

## **6. Sort Data (`ORDER BY`)**
### **Query:**
```sql
SELECT * FROM dataset_1 ORDER BY coupon;
```
### **Explanation:**
- Sorts the result **in ascending order** based on the `coupon` column.

### **Result Set (Sorted by `coupon`):**
| id | destination | weather | temperature | passanger | coupon |
|----|------------|---------|------------|-----------|--------|
| 3  | Park       | Rainy   | 18         | Alone     | 3      |
| 1  | Home       | Sunny   | 30         | Alone     | 5      |
| 2  | Office     | Cloudy  | 22         | Group     | 10     |

---

## **7. Rename Column (`AS`)**
### **Query:**
```sql
SELECT destination AS Destination FROM dataset_1;
```
### **Explanation:**
- Renames the `destination` column as `Destination`.

### **Result Set:**
| Destination |
|------------|
| Home       |
| Office     |
| Park       |

---

## **8. Grouping Data (`GROUP BY`)**
### **Query:**
```sql
SELECT occupation FROM dataset_1 GROUP BY occupation;
```
### **Explanation:**
- Groups rows by `occupation`, **returning unique occupation types**.

### **Result Set:**
| occupation |
|-----------|
| Student   |
| Engineer  |
| Manager   |

---

## **9. Average Calculation (`AVG()`)**
### **Query:**
```sql
SELECT weather, AVG(temperature) AS avg_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Calculates the **average temperature** for each `weather` type.

### **Result Set:**
| weather | avg_temp |
|---------|---------|
| Sunny   | 30      |
| Cloudy  | 22      |
| Rainy   | 18      |

---

## **10. Counting Rows (`COUNT()`)**
### **Query:**
```sql
SELECT weather, COUNT(temperature) AS count_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Counts the **number of rows** for each `weather` type.

### **Result Set:**
| weather | count_temp |
|---------|------------|
| Sunny   | 1          |
| Cloudy  | 1          |
| Rainy   | 1          |

---

## **11. Counting Unique Values (`COUNT(DISTINCT)`)**
### **Query:**
```sql
SELECT weather, COUNT(DISTINCT temperature) AS count_distinct_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Counts **only distinct temperatures** for each `weather` type.

### **Result Set (Same as `COUNT(temperature)`, but ensures uniqueness):**
| weather | count_distinct_temp |
|---------|---------------------|
| Sunny   | 1                   |
| Cloudy  | 1                   |
| Rainy   | 1                   |

---

## **12. Sum of Values (`SUM()`)**
### **Query:**
```sql
SELECT weather, SUM(temperature) AS sum_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Sums up all temperatures for each `weather` type.

### **Result Set:**
| weather | sum_temp |
|---------|---------|
| Sunny   | 30      |
| Cloudy  | 22      |
| Rainy   | 18      |

---

## **13. Minimum Value (`MIN()`)**
### **Query:**
```sql
SELECT weather, MIN(temperature) AS min_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Retrieves the **minimum temperature** for each `weather` type.

### **Result Set:**
| weather | min_temp |
|---------|---------|
| Sunny   | 30      |
| Cloudy  | 22      |
| Rainy   | 18      |

---

## **14. Maximum Value (`MAX()`)**
### **Query:**
```sql
SELECT weather, MAX(temperature) AS max_temp FROM dataset_1 GROUP BY weather;
```
### **Explanation:**
- Retrieves the **maximum temperature** for each `weather` type.

### **Result Set:**
| weather | max_temp |
|---------|---------|
| Sunny   | 30      |
| Cloudy  | 22      |
| Rainy   | 18      |

---

## **15. Filtering Groups (`HAVING`)**
### **Query:**
```sql
SELECT occupation FROM dataset_1 GROUP BY occupation HAVING occupation='Student';
```
### **Explanation:**
- Groups by `occupation`, then **filters out only `'Student'`**.

### **Result Set:**
| occupation |
|-----------|
| Student   |

---

### **🔹 Summary Table**
| SQL Clause  | Purpose |
|-------------|---------|
| `SELECT *` | Retrieves all data |
| `SELECT column1, column2` | Retrieves specific columns |
| `LIMIT n` | Limits the number of rows |
| `DISTINCT` | Selects unique values |
| `WHERE` | Filters data |
| `ORDER BY` | Sorts data |
| `AS` | Renames columns |
| `GROUP BY` | Groups data |
| `AVG()` | Calculates average |
| `COUNT()` | Counts rows |
| `SUM()` | Sums values |
| `MIN()` | Gets minimum value |
| `MAX()` | Gets maximum value |
| `HAVING` | Filters grouped data |


The three SQL clauses used in your queries are:  

1. **`JOIN` Clause**  
2. **`WHERE` Clause**  
3. **`BETWEEN` Clause**  

Let's go step by step, using sample tables to explain each clause.  

---

## **1. `JOIN` Clause** (Combining Data from Multiple Tables)  

### **Query:**
```sql
SELECT a.destination, a.time, b.part_of_day 
FROM dataset_1 a 
INNER JOIN table_to_join b 
ON a.time = b.time;
```

### **Explanation:**  
- `INNER JOIN` combines data from `dataset_1` and `table_to_join` **where the `time` column matches in both tables**.  
- It returns only the matching rows.  

### **Example Tables:**  

#### **Table: `dataset_1`**
| id  | destination | time  | weather |
|-----|------------|-------|---------|
| 1   | Paris      | 08:00 | Sunny   |
| 2   | London     | 12:00 | Cloudy  |
| 3   | Tokyo      | 20:00 | Rainy   |

#### **Table: `table_to_join`**
| time  | part_of_day |
|-------|------------|
| 08:00 | Morning    |
| 12:00 | Afternoon  |
| 20:00 | Night      |

### **Query Execution:**  
1. `INNER JOIN` looks for **matching `time` values** in both tables.
2. It combines columns from both tables into one result.

### **Result Set:**  
| destination | time  | part_of_day |
|------------|-------|------------|
| Paris      | 08:00 | Morning    |
| London     | 12:00 | Afternoon  |
| Tokyo      | 20:00 | Night      |

---

## **2. `WHERE` Clause** (Filtering Rows)  

### **Query 1:** (Filtering passengers traveling alone)
```sql
SELECT destination, passanger  
FROM (SELECT * FROM dataset_1 WHERE passanger = 'Alone');
```
- This selects only the rows where the `passanger` column is `'Alone'`.  

#### **Table: `dataset_1`**
| id  | destination | passanger   | time  |
|-----|------------|------------|-------|
| 1   | Paris      | Alone      | 08:00 |
| 2   | London     | Group      | 12:00 |
| 3   | Tokyo      | Alone      | 20:00 |

### **Result Set:**  
| destination | passanger |
|------------|------------|
| Paris      | Alone      |
| Tokyo      | Alone      |

---

### **Query 2:** (Filtering weather starting with "Sun")
```sql
SELECT * FROM dataset_1 WHERE weather LIKE 'Sun%';
```
- `LIKE 'Sun%'` finds all rows where `weather` starts with **"Sun"** (e.g., "Sunny", "Sunlight").  
- `%` is a **wildcard** that matches any characters after "Sun".

#### **Example Table: `dataset_1`**
| id  | destination | weather   |
|-----|------------|-----------|
| 1   | Paris      | Sunny     |
| 2   | London     | Cloudy    |
| 3   | Tokyo      | Sunlight  |

### **Result Set:**  
| destination | weather   |
|------------|-----------|
| Paris      | Sunny     |
| Tokyo      | Sunlight  |

---

## **3. `BETWEEN` Clause** (Selecting a Range of Values)  

### **Query:** (Filtering temperatures between 29 and 75)
```sql
SELECT DISTINCT temperature 
FROM dataset_1 WHERE temperature BETWEEN 29 AND 75;
```
- `BETWEEN 29 AND 75` filters **only temperatures within this range** (both 29 and 75 are included).  
- `DISTINCT` ensures no duplicate temperatures are shown.

#### **Example Table: `dataset_1`**
| id  | temperature |
|-----|------------|
| 1   | 30         |
| 2   | 50         |
| 3   | 80         |
| 4   | 75         |
| 5   | 29         |

### **Result Set:**  
| temperature |
|------------|
| 30         |
| 50         |
| 75         |
| 29         |

---

## **4. `IN` Clause** (Selecting Specific Values)  

### **Query:** (Filtering occupations)
```sql
SELECT occupation FROM dataset_1 
WHERE occupation IN ('Sales & Related', 'Management');
```
- This filters rows where `occupation` is **either** `'Sales & Related'` or `'Management'`.

#### **Example Table: `dataset_1`**
| id  | name  | occupation       |
|-----|-------|-----------------|
| 1   | Alice | Sales & Related |
| 2   | Bob   | Engineer        |
| 3   | Eve   | Management      |

### **Result Set:**  
| occupation       |
|-----------------|
| Sales & Related |
| Management      |

---

### **Summary**
| Clause   | Purpose |
|----------|---------|
| `JOIN`   | Combines data from multiple tables based on a common column. |
| `WHERE`  | Filters rows based on a condition before grouping or aggregation. |
| `BETWEEN` | Selects values within a range (inclusive). |
| `LIKE`    | Finds values matching a pattern. |
| `IN`      | Selects rows that match specific values. |

Would you like me to add more details or another example? 😊
