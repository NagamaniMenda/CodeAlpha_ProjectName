
# CodeAlpha_ProjectName

# 🎮 Hangman Game

![image alt]([https://github.com/NagamaniMenda/CodeAlpha_ProjectName/blob/459140f1bd331f935a4ca034f1b2e34dbc22659a/hangman.JPG](https://github.com/NagamaniMenda/CodeAlpha_ProjectName/blob/main/hangman.JPG))

## Description
A simple Python console game where the player guesses a hidden word one letter at a time. Correct guesses reveal letters, wrong guesses reduce tries. Fun, interactive, and beginner-friendly.

## Features
- Random word selection from a predefined list
- Keeps track of guessed letters
- Prevents duplicate guesses
- Displays remaining tries after each turn
- Friendly messages with emojis

## How to Run in Jupyter Notebook
1. Open this repository in Jupyter Notebook or JupyterLab.
2. Open a new code cell.
3. Copy and paste the code below into the cell.
4. Run the cell to start the Hangman game.
5. Follow the on-screen prompts to guess letters.

## Example Gameplay
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

## Code
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
if __name__ == "__main__":
    hangman()
```

Project Info

Language: Python

Type: Console-based Game

Level: Beginner-friendly

    hangman()
