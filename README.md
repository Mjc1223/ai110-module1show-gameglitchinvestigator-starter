# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- The game's purpose is to let the user guess a secret number within a limited range of numbers and attempts based on the selection of difficulty.
- While testing the game there were multiple bugs. One bug was the hint logic not correlating with the actual secret number. Another bug was empty input handling, where quotation marks would appear instead of properly prompting me to enter a guess. I also noticed that the submit guess button had to be clicked more than once before the game updated and responded.
- To fix these issues, I used AI assistance and reviewed the game logic in `app.py` and `logic_utils.py`. I fixed the inconsistent type conversion between strings and integers, which corrected the hint mismatch bug. I verified my fixes by running pytest, where all four tests passed, and by manually testing the game in Streamlit.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User starts the game and is prompted to guess a number, the number of attempts and the range of numbers to guess from is based on difficulty.
2. User enters a guess of 50.
3. Game returns "Go HIGHER!"
4. User enters a guess of 55.
5. Game returns "Go LOWER!"
6. Score updates correctly after each guess is made.
7. The game ends once the user guesses correctly or runs out of attempts.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
python -m pytest -q
....                                                                                                                                              [100%]
4 passed in 0.03


## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
