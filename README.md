# 🎲 LotteryGame (Java)

A console-based **Lottery Game simulator** implemented in Java. Players pick **5 unique numbers** (1–69). The computer draws 5 unique numbers at random. You earn **$100 per match**, and if you match all 5 you win the **jackpot**. The jackpot **starts at $10,000,000** and **rolls over by $2,000,000** after non-jackpot games.

---

## ✨ Features

- Input validation (unique picks, range 1–69, integer-only)
- **Rolling jackpot**: resets on win, increases otherwise
- Game loop with **play again** prompt
- Per-game breakdown and **final session summary**
- Compact, readable OOP design

---

## 🧮 Game Rules

- Pick **5 distinct integers** from **1** to **69**
- Each match (player vs. computer) pays **$100**
- **Match all 5** → win the **current jackpot**
- If the jackpot is **not** won, it **increases by $2,000,000**
- Jackpot resets to **$10,000,000** on a win

> This is a probability demo/simulator for learning purposes — **no real money**.

---

## ⚙️ Configuration (Constants)

Edit the constants in `LotteryGame.java` to tweak the game:

```java
private static final int INITIAL_JACKPOT = 10000000; // $10,000,000
private static final int JACKPOT_INCREMENT = 2000000; // +$2,000,000 when not hit
private static final int NUMBER_OF_PICKS = 5;
private static final int RANGE = 69; // valid values: 1..69
```

---

## 🧱 Project Structure

```
lottery-game/
├─ src/
│  └─ LotteryGame/
│     └─ LotteryGame.java
├─ README.md
└─ .gitignore
```

> Package name is `LotteryGame`, so the folder structure must match.

---

## 🚀 Build & Run

### Prerequisites
- Java 11+ (Java 17 recommended)
- Terminal / Command Prompt

### Compile
```bash
# from project root
javac -d out src/LotteryGame/LotteryGame.java
```

### Run
```bash
java -cp out LotteryGame.LotteryGame
```

---

## 🧭 Sample Session

```
Enter 5 unique numbers between 1 and 69:
1
7
23
41
69
Player's numbers: 1 7 23 41 69
Computer's numbers: 4 7 16 41 60
Numbers matched: 2
Winnings this game: $200
Do you want to play again? (yes/no)
yes
...
Final Results:
Total games played: 3
Total numbers matched: 5
Total winnings: $500
Final jackpot value: $14000000
```

---

## 🧠 Code Overview

- `LotteryGame` (single-class executable)
  - `generateComputerNumbers()` – random unique draw (Set → int[])
  - `getPlayerNumbers(Scanner)` – input with validation
  - `checkMatches(int[], int[])` – count intersections
  - `printCurrentGameResults(...)` – display per-game result
  - `printFinalResults()` – session summary
  - `play()` – main game loop (jackpot logic, replay)
  - `main(String[] args)` – entry point

---

## ✅ Validation & Error Handling

- Non-integer input is handled via `try/catch` with retry
- Duplicate or out-of-range numbers trigger a helpful message
- Ensures the player provides exactly 5 valid, distinct picks

---

## 🗺️ Roadmap (Ideas)

- “Powerball”/bonus number variant
- Track **per-game history** and export to CSV
- Difficulty presets (different ranges / pay tables)
- Deterministic mode for testing (`Random(seed)`)
- Unit tests (JUnit) + CI (GitHub Actions)
- GUI (Swing/JavaFX) or web version (Spring Boot)

---

## 🧰 Suggested `.gitignore`

```
/out/
*.class
*.log
# IDE
.vscode/
.idea/
*.iml
# OS
.DS_Store
Thumbs.db
```


## 📜 License

MIT — free to use, modify, and distribute for educational purposes.
