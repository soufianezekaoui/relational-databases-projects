# 💇‍♂️💇 Salon Appointment Scheduler

A simple **command-line appointment booking system** built with **PostgreSQL and Bash**.
This project simulates how a salon schedules customer appointments using a relational database.

Built as part of the **freeCodeCamp Relational Database Certification**.

---

## 📌 Project Overview

This application allows users to:

* View available salon services
* Book appointments from the terminal
* Register new customers automatically
* Store appointments in a PostgreSQL database

The system checks if a phone number already exists and links appointments to the correct customer.

---

## 🗄️ Database Schema

### `customers`

| column      | type             |
| ----------- | ---------------- |
| customer_id | SERIAL (PK)      |
| phone       | VARCHAR (UNIQUE) |
| name        | VARCHAR          |

### `services`

| column     | type        |
| ---------- | ----------- |
| service_id | SERIAL (PK) |
| name       | VARCHAR     |

### `appointments`

| column         | type           |
| -------------- | -------------- |
| appointment_id | SERIAL (PK)    |
| customer_id    | FK → customers |
| service_id     | FK → services  |
| time           | VARCHAR        |

---

## ⚙️ Technologies Used

* **PostgreSQL**
* **SQL**
* **Bash Scripting**
* **Command Line Interface**

---

## 📂 Project Structure

```
salon-appointment-scheduler
│
├── README.md
├── examples.txt  # Output examples
├── salon.sh      # Bash application
└── salon.sql     # Database dump
```

---

## ▶️ Running the Project

1️⃣ Create the database

```
CREATE DATABASE salon;
```

2️⃣ Run the scheduler

```
./salon.sh
```

3️⃣ Choose a service and book your appointment.

---

## 💡 Example

```
1) cut
2) color
3) perm

What's your phone number?
061-954-9550

What time would you like your cut, Saski?

I have put you down for a cut at 16:00, Saski.
```

---

## 🎓 What I Learned

* Relational database design
* SQL queries with PostgreSQL
* Bash scripting for interactive programs
* Database-driven CLI applications

---

## 👨‍💻 Author

**Soufiane ZEKAOUI**
- GitHub:   [soufianezekaoui](https://github.com/soufianezekaoui)
- LinkedIn: [Soufiane Zekaoui](https://linkedin.com/in/soufiane-zekaoui-445b1b352/)
- Portfolio: [My-Personal-Website](https://soufianezekaoui.github.io/my_soufianeze_portfolio/)

## ⭐ Acknowledgements

 - freeCodeCamp for the project and testing environment
 - PostgreSQL community for excellent documentation

✨ Feel free to fork this repository, explore the database, or build upon it!
