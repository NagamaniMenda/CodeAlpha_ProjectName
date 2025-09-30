<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4746e77d-bb92-4797-b377-c9efedcb5ba7" /># CodeAlpha_ProjectName
**Hangman Game:** A simple Python console game where the player guesses a hidden word letter by letter. Correct guesses reveal letters, wrong guesses reduce tries. Fun, beginner-friendly, and interactive with emojis for feedback.


Ah! Got it ✅ You want **everything—including code—inside one single Markdown block** so you can just copy-paste into your `README.md`. Here’s the **all-in-one block**:

````markdown
# 🎮 Hangman Game

## 📌 Description
A simple Python console game where the player guesses a hidden word one letter at a time. Correct guesses reveal letters, wrong guesses reduce tries. Fun, interactive, and beginner-friendly.

## 🛠️ Features
- Random word selection from a predefined list
- Keeps track of guessed letters
- Prevents duplicate guesses
- Displays remaining tries after each turn
- Friendly messages with emojis

## ▶️ How to Run
1. Make sure you have **Python 3** installed.
2. Save the file as `hangman.py`.
3. Run in a terminal or command prompt:
```bash
python hangman.py
````

4. Follow the on-screen instructions to play.

## 🎯 Example Gameplay

```
🎮 Welcome to Hangman Game!
_ _ _ _ _

Guess a letter: a
✅ Correct guess!
Word: a _ a _ a
Remaining tries: 6

Guess a letter: z
❌ Wrong guess!
Word: a _ a _ a
Remaining tries: 5
```

---

## 📝 Code

```python
import random

def hangman():
    words = ["apple", "banana", "grape", "mango", "orange"]
    word = random.choice(words)
    guessed_letters = []
    tries = 6
    guessed = False

    print("🎮 Welcome to Hangman Game!")
    print("_ " * len(word))

    while not guessed and tries > 0:
        guess = input("\nGuess a letter: ").lower()

        if len(guess) == 1 and guess.isalpha():
            if guess in guessed_letters:
                print("⚠️ You already guessed that letter.")
            elif guess not in word:
                print("❌ Wrong guess!")
                tries -= 1
                guessed_letters.append(guess)
            else:
                print("✅ Correct guess!")
                guessed_letters.append(guess)
        else:
            print("⚠️ Invalid input. Please enter a single letter.")

        word_display = ""
        for letter in word:
            if letter in guessed_letters:
                word_display += letter + " "
            else:
                word_display += "_ "

        print("Word:", word_display)
        print("Remaining tries:", tries)

        if "_" not in word_display:
            guessed = True

    if guessed:
        print("\n🎉 Congratulations! You guessed the word:", word)
    else:
        print("\n💀 Game Over! The word was:", word)

# Start the game
if __name__ == "__main__":
    hangman()
```

---

## 📂 Project Info

* **Language:** Python
* **Type:** Console-based Game
* **Level:** Beginner-friendly

```

✅ This is **one block** including **description, instructions, example, and exactly your code**. You can copy it straight into `README.md`.  

If you want, I can also make a **super compact version** where the whole thing fits even cleaner for GitHub. Do you want me to do that?
```
