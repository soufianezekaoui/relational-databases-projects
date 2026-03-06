# ⚽ World Cup Database (PostgreSQL + Bash)

A relational database project that stores and analyzes **FIFA World Cup knockout stage matches (2014 & 2018)** using **PostgreSQL**, **Bash scripting**, and **SQL queries**.

This project was built as part of the **freeCodeCamp Relational Database Certification** and demonstrates practical skills in:

* Database design
* SQL queries
* Data normalization
* Bash scripting
* Data import automation
---

## 📌 Project Overview

The project performs three main tasks:

1. **Database Design**

   * Create a relational schema for teams and games.

2. **Automated Data Import**

   * Use a Bash script to read a CSV file and populate the database.

3. **Data Analysis**

   * Execute SQL queries to extract insights from the tournament data.

---

## 🗄️ Database Schema

### `teams` table

| Column  | Type    | Description      |
| ------- | ------- | ---------------- |
| team_id | SERIAL  | Primary Key      |
| name    | VARCHAR | Unique team name |

### `games` table

| Column         | Type    | Description              |
| -------------- | ------- | ------------------------ |
| game_id        | SERIAL  | Primary Key              |
| year           | INT     | Tournament year          |
| round          | VARCHAR | Stage of the match       |
| winner_id      | INT     | Winning team             |
| opponent_id    | INT     | Opponent team            |
| winner_goals   | INT     | Goals scored by winner   |
| opponent_goals | INT     | Goals scored by opponent |

Relationships:

* One **team** can participate in many **games**
* `winner_id` and `opponent_id` reference `teams.team_id`

---

## 📂 Project Structure

```
worldcup-database
│
├── games.csv        # Raw dataset of World Cup matches
├── insert_data.sh   # Script to import CSV data into PostgreSQL
├── queries.sh       # SQL queries for tournament statistics
├── worldcup.sql     # Database dump (required for submission)
└── README.md
```

---

## ⚙️ Technologies Used

* **PostgreSQL**
* **SQL**
* **Bash**
* **CSV Data Processing**

---

## 🚀 Example Insights

The project answers questions such as:

* Total goals scored in the tournament
* Average goals per game
* Teams that played in specific rounds
* Tournament champions
* Teams starting with specific patterns

Example query:

```sql
SELECT name
FROM teams
JOIN games ON teams.team_id = games.winner_id
WHERE year = 2018 AND round = 'Final';
```

Result:

```
France
```

---

## ▶️ Running the Project

1️⃣ Create the database

```
CREATE DATABASE worldcup;
```

2️⃣ Import the data

```
./insert_data.sh
```

3️⃣ Run the queries

```
./queries.sh
```

---

## 🎓 Learning Outcomes

Through this project I practiced:

* Relational database design
* Primary & foreign key relationships
* SQL aggregation queries
* Bash automation for database workflows
* Data ingestion from CSV files

---

## 👨‍💻 Author

**Soufiane ZEKAOUI**
- GitHub: [@soufianezekaoui](https://github.com/soufianezekaoui)
- LinkedIn: [Soufiane Zekaoui](https://linkedin.com/in/soufiane-zekaoui-445b1b352/)
- Portfolio: [My-Personal-Website](https://soufianezekaoui.github.io/my_soufianeze_portfolio/)

---

⭐ If you found this project useful or interesting, feel free to **star the repository**!

---
