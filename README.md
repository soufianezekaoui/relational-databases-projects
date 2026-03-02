# 🌌 Celestial Bodies Database

A relational PostgreSQL database that models the structure of the universe — galaxies, stars, planets, and moons — built as part of the **freeCodeCamp Relational Database Certification**.

This project demonstrates database design, normalization, constraints, and relationships using **PostgreSQL**.

---

## 📌 Project Overview

The **Celestial Bodies Database** is designed to represent astronomical objects and their relationships:

- 🌠 Galaxies contain stars  
- ⭐ Stars host planets  
- 🪐 Planets have moons  

The database follows best practices for relational design, including:
- Primary keys
- Foreign keys
- Data constraints
- Type consistency
- Uniqueness rules

---

## 🧱 Database Structure

### 📂 Tables

| Table         | Description                             |
|---------------|-----------------------------------------|
| `galaxy`      | Stores galaxy data                      |
| `star`        | Stores stars and links them to galaxies |
| `planet`      | Stores planets and links them to stars  |
| `moon`        | Stores moons and links them to planets  |
| `planet_type` | Stores planet classifications           |

---

### 🔑 Key Features

- Auto-incremented primary keys (`table_name_id`)
- Proper foreign key relationships
- Enforced `UNIQUE` and `NOT NULL` constraints
- Use of multiple PostgreSQL data types:
  - `VARCHAR`
  - `INT`
  - `NUMERIC`
  - `TEXT`
  - `BOOLEAN`
- Realistic and creative astronomical data

---

## 🧪 Project Requirements (freeCodeCamp)

✔ Database named `universe`  
✔ At least **5 tables**  
✔ Proper foreign key relationships  
✔ Minimum row counts met  
✔ All tests passed successfully  
✔ SQL dump provided  

---

## 🚀 How to Use

### 1️⃣ Restore the Database

Make sure PostgreSQL is installed, then run:

```bash
psql -U postgres < universe.sql

### 2️⃣ Connect to the Database

```bash
psql -U postgres
\c universe
```

### 3️⃣ Explore the Data

```SQL
SELECT * FROM galaxy;
SELECT * FROM star;
SELECT * FROM planet;
SELECT * FROM moon;
```

## 🛠 Technologies Used

 - PostgreSQL
 - psql
 - SQL
 - Git & GitHub
 - freeCodeCamp Virtual Machine

## 🎓 Certification

This project was completed as part of:
freeCodeCamp — Relational Database Certification

## 👤 Author

Soufiane Zekaoui
🎓 Engineering Student – Information Systems
🌍 Morocco

## ⭐ Acknowledgements

 - freeCodeCamp for the project and testing environment
 - PostgreSQL community for excellent documentation

✨ Feel free to fork this repository, explore the database, or build upon it!
