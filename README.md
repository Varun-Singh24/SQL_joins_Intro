
# 📌 SQL JOINS Practice

This repository demonstrates the use of **SQL JOIN operations** to combine data from two tables.  
JOINs are essential for working with relational databases where data is stored across multiple tables.

---

## 📂 Tables Used

- **people**
- **states**

These tables are linked using:
- `people.state_code`
- `states.state_abbrev`

---

## 🔗 What is a JOIN?

A JOIN is used to **combine rows from two or more tables** based on a related column between them.

---

## 1️⃣ INNER JOIN (Basic JOIN)

### 🧾 Code
```sql
SELECT people.first_name, people.state_code, states.division
FROM people
JOIN states
ON people.state_code = states.state_abbrev;
````

### 📘 Explanation

* Combines rows where `state_code` matches `state_abbrev`
* Returns only matching records from both tables

### 🎯 Use Case

✔ Mapping users to their state divisions
✔ Combining customer data with location data

---

## 2️⃣ Selecting All Columns

### 🧾 Code

```sql
SELECT *
FROM people
JOIN states
ON people.state_code = states.state_abbrev;
```

### 📘 Explanation

* Retrieves all columns from both tables
* Useful for debugging or full data inspection

### 🎯 Use Case

✔ Data exploration
✔ Schema validation

---

## 3️⃣ JOIN with Conditions (Filtering)

### 🧾 Code

```sql
SELECT *
FROM people
JOIN states 
ON people.state_code = states.state_abbrev
WHERE states.region = 'South' 
AND people.first_name LIKE 'J%';
```

### 📘 Explanation

* Filters joined data based on:

  * Region = South
  * Names starting with 'J'
* Combines JOIN + WHERE clause

### 🎯 Use Case

✔ Region-based user analysis
✔ Targeted marketing (e.g., users with specific names)

---

## 4️⃣ Implicit JOIN (Old Style)

### 🧾 Code

```sql
SELECT people.first_name, states.state_name
FROM people, states
WHERE people.state_code = states.state_abbrev;
```

### 📘 Explanation

* Uses `FROM table1, table2` syntax
* Join condition is written in WHERE clause

### ⚠️ Note

* Less readable than modern JOIN syntax
* Not recommended for complex queries

### 🎯 Use Case

✔ Legacy SQL systems
✔ Understanding SQL fundamentals

---

## 🚀 Real-World Use Cases

✔ Customer & Order data merging
✔ Employee & Department mapping
✔ Location-based analytics 


## 🤝 Contributing

