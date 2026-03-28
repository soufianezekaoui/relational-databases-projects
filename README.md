# 🧪 Periodic Table Database

A command-line tool that retrieves chemical element information from a **PostgreSQL database**.

This project demonstrates **database normalization, data cleaning, relational queries, and Bash scripting** using a simplified periodic table dataset.

Built as part of the **freeCodeCamp Relational Database Certification**.

---

## 📌 Project Overview

The project improves an existing database and provides a **CLI program** that allows users to search for chemical elements by:

* Atomic number
* Element symbol
* Element name

The program then displays key properties of the element.

---

## 🗄️ Database Schema

### `elements`

| column        | type             |
| ------------- | ---------------- |
| atomic_number | INT (PK)         |
| symbol        | VARCHAR (UNIQUE) |
| name          | VARCHAR (UNIQUE) |

### `properties`

| column                | type          |
| --------------------- | ------------- |
| atomic_number         | FK → elements |
| atomic_mass           | DECIMAL       |
| melting_point_celsius | NUMERIC       |
| boiling_point_celsius | NUMERIC       |
| type_id               | FK → types    |

### `types`

| column  | type     |
| ------- | -------- |
| type_id | INT (PK) |
| type    | VARCHAR  |

---

## ⚙️ Technologies Used

* **PostgreSQL**
* **SQL**
* **Bash**
* **Git**

---

## 📂 Project Structure

```
periodic-table-database
│
├── README.md
├── element.sh           # CLI program
├── atomic_mass.txt
└── periodic_table.sql   # Database dump
```

---

## ▶️ Usage

Run the script with an element identifier:

```
./element.sh 1
./element.sh H
./element.sh Hydrogen
```

Example output:

```
The element with atomic number 1 is Hydrogen (H). 
It's a nonmetal, with a mass of 1.008 amu. 
Hydrogen has a melting point of -259.1 celsius and a boiling point of -252.9 celsius.
```

If the element doesn't exist:

```
I could not find that element in the database.
```

---

## 🎓 What I Learned

* Database normalization and schema design
* SQL constraints and foreign keys
* Data cleaning and transformation
* Bash scripting with PostgreSQL queries
* Version control using Git

---

## 👨‍💻 Author

**Soufiane ZEKAOUI**
- GitHub: [@soufianezekaoui](https://github.com/soufianezekaoui)
- LinkedIn: [Soufiane Zekaoui](https://linkedin.com/in/soufiane-zekaoui-445b1b352/)
- Portfolio: [My-Personal-Website](https://soufianezekaoui.github.io/my_soufianeze_portfolio/)

---

⭐ If you found this project useful or interesting, feel free to **star the original repo**!
