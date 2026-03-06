# ⚽ World Cup Database (PostgreSQL + Bash)

A relational database project that stores and analyzes **FIFA World Cup knockout stage games** from 2014 and 2018 using **PostgreSQL**.
The project automatically imports match data from a CSV file using a **Bash script**, and performs analytical queries using **SQL**.

This project is part of the **Relational Database Certification** from freeCodeCamp and demonstrates practical skills in:

* Database design
* SQL queries
* Data normalization
* Bash scripting
* Data import automation

---

# 📊 Dataset

The dataset contains results from the **final stages of the FIFA World Cup tournaments**.

Included rounds:

* Final
* Third Place
* Semi-Final
* Quarter-Final
* Eighth-Final

Each record contains:

* Year
* Round
* Winning team
* Opponent team
* Goals scored by each team

Example:

```
year,round,winner,opponent,winner_goals,opponent_goals
2018,Final,France,Croatia,4,2
2014,Final,Germany,Argentina,1,0
```

---

# 🗄️ Database Structure

The database follows **relational design principles** with two main tables.

## Teams Table

Stores the list of unique national teams.

| Column  | Type    | Description      |
| ------- | ------- | ---------------- |
| team_id | SERIAL  | Primary key      |
| name    | VARCHAR | Unique team name |

---

## Games Table

Stores all match results.

| Column         | Type    | Description              |
| -------------- | ------- | ------------------------ |
| game_id        | SERIAL  | Primary key              |
| year           | INT     | Tournament year          |
| round          | VARCHAR | Stage of tournament      |
| winner_id      | INT     | Foreign key → teams      |
| opponent_id    | INT     | Foreign key → teams      |
| winner_goals   | INT     | Goals scored by winner   |
| opponent_goals | INT     | Goals scored by opponent |

Relationships:

```
teams (1) ---- (many) games
```

Each game references two teams:

* the **winner**
* the **opponent**

---

# 🛠️ Technologies Used

* **PostgreSQL**
* **SQL**
* **Bash scripting**
* **CSV data import**
* **Git & GitHub**

---

# 📂 Project Structure

```
worldcup-database
│
├── games.csv
├── insert_data.sh
├── queries.sh
├── worldcup.sql
└── README.md
```

| File           | Description                                  |
| -------------- | -------------------------------------------- |
| games.csv      | Raw dataset of World Cup matches             |
| insert_data.sh | Script that imports CSV data into PostgreSQL |
| queries.sh     | Script that runs analytical SQL queries      |
| worldcup.sql   | Full database dump                           |
| README.md      | Project documentation                        |

---

# ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```
git clone https://github.com/soufianezekaoui/worldcup-database.git
cd worldcup-database
```

---

### 2️⃣ Create the database

Open PostgreSQL:

```
psql --username=freecodecamp --dbname=postgres
```

Create database:

```
CREATE DATABASE worldcup;
```

Connect to it:

```
\c worldcup
```

---

### 3️⃣ Create tables

Run the SQL commands inside `worldcup.sql` or create them manually.

---

### 4️⃣ Import data

Make the script executable:

```
chmod +x insert_data.sh
```

Run the script:

```
./insert_data.sh
```

This script will:

* Insert unique teams
* Insert all match records
* Automatically map foreign keys

---

# 🔎 Example Queries

The project includes several analytical queries such as:

### Total goals scored by winning teams

```
SELECT SUM(winner_goals) FROM games;
```

### Tournament champions

```
SELECT year, name
FROM games
JOIN teams ON winner_id = team_id
WHERE round = 'Final';
```

### Teams that played in the 2014 Eighth-Final

```
SELECT name
FROM teams
JOIN games ON team_id = winner_id
WHERE year = 2014 AND round = 'Eighth-Final';
```

---

# 📈 Skills Demonstrated

This project demonstrates:

* Relational database modeling
* Primary & foreign keys
* Data normalization
* SQL aggregations (`SUM`, `AVG`, `COUNT`)
* JOIN operations
* Bash automation with PostgreSQL
* Data import from CSV

---

# 🎓 Certification

This project was completed as part of the **freeCodeCamp Relational Database Certification**.

---

# 👨‍💻 Author

**Soufiane Zekaoui**

Software Engineering Student
Management & Governance of Information Systems

---

# ⭐ Acknowledgements

* freeCodeCamp
* PostgreSQL Documentation
* FIFA World Cup Data
