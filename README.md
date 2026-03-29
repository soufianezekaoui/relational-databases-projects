# 🎯 Number Guessing Game — PostgreSQL + Bash

An interactive **command-line game** where users guess a randomly generated number between **1 and 1000**, with persistent data storage using **PostgreSQL**.

This project goes beyond a simple game — it introduces **stateful user tracking**, **performance analytics**, and **database-driven logic**.

---

## 🚀 Features

* 🎲 Random number generation (1 → 1000)
* 👤 User authentication via username
* 📊 Tracks:

  * Number of games played
  * Best performance (minimum guesses)
* 🔁 Real-time feedback:

  * "higher" / "lower" hints
* 🧠 Input validation (handles non-integer inputs)
* 💾 Persistent storage using PostgreSQL

---

## 🗄️ Database Design

### `users`

| Column   | Type        | Description     |
| -------- | ----------- | --------------- |
| user_id  | SERIAL      | Primary Key     |
| username | VARCHAR(22) | Unique username |

### `games`

| Column  | Type   | Description        |
| ------- | ------ | ------------------ |
| game_id | SERIAL | Primary Key        |
| user_id | INT    | Reference to user  |
| guesses | INT    | Number of attempts |

📌 Relationship:

* One user → many games
* Each game stores performance data

---

## 🧠 How It Works

1. User enters a username
2. System checks:

   * Existing user → shows stats
   * New user → creates profile
3. Game starts:

   * User guesses the number
   * System gives hints
4. On success:

   * Score is saved in database

---

## ▶️ Usage

```bash
./number_guess.sh
```

### Example

```
Enter your username:
soufianeze

Welcome back, soufianeze! You have played 3 games, and your best game took 4 guesses.

Guess the secret number between 1 and 1000:
500
It's higher than that, guess again:
750
You guessed it in 2 tries. The secret number was 750. Nice job!
```

---

## 🛠 Tech Stack

* **PostgreSQL** → Data persistence
* **SQL** → Queries & analytics
* **Bash** → CLI logic & control flow
* **Git** → Version control

---

## 🎓 What This Project Demonstrates

* Designing relational schemas
* Writing efficient SQL queries (COUNT, MIN)
* Handling user input in CLI apps
* Building stateful applications
* Connecting backend logic with a database

---

## 💡 Why This Project Matters

This project simulates a **real backend pattern**:

➡️ User → Interaction → Data Storage → Analytics

It reflects how real systems:

* Track users
* Store behavior
* Optimize based on performance

---

## 👨‍💻 Author

**Soufiane ZEKAOUI**
- GitHub: [@soufianezekaoui](https://github.com/soufianezekaoui)
- LinkedIn: [Soufiane Zekaoui](https://linkedin.com/in/soufiane-zekaoui-445b1b352/)
- Portfolio: [My-Personal-Website](https://soufianezekaoui.github.io/my_soufianeze_portfolio/)

---

⭐ If you found this project useful or interesting, feel free to **star the original repo**!
