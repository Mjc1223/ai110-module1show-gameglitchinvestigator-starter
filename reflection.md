# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it? When I loaded the game, it loaded successfully and from a glance it seems like everything works out fine. However, as I continued throughout the game I see that several parts of the game did not work correctly. Some guesses caused unexpected results and the game logic did not always handle the inputs correctly. I also noticed many issues with the score updates and hint behavior while testing different inputs. Through me doing this I was able to identify certain bus and begin fixing them one at a time.
- List at least two concrete bugs you noticed at the start  The two concrete bugs that I noticed at the start of the start of the game was the attempts bug and the hints. The attempt bug was that the game listed 7 attempts, but it had already said that I used an attempt when I did not even input anything in yet. The hint bug was that it would tell me to go higher than the secret number when I inputted a number that was higher than the secret number instead of telling me to go lower.
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|70 | GO HIGHER! | GO LOWER! |None |
| Empty input|Prompt user to enter a guess|It said "Enter a guess." |None |
| 70.5|GO HIGHER!|GO LOWER! |None |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)? 
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result). 
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
The AI tools that I used on this project were chatgpt and Copilot. After finding a bugh where the game's hints did not match the secret number correctly, I asked the AI to help explain the logic and identify where the issue might be occuring. One example that the AI suggested that was correct was reviewing the comparison logic in the guessing functions and checking the related test files. I verified the suggestion by running the game, testing different guesses, and running the pytest tests until the behavior matched the expected outputs. One thing I noticed during this project was that most of the AI suggestions were accurate and helpful. I did not run into any issues at all. However, I stiil made sure to verify each change made by running pytest and manually testing the game in Streamlit. This showed that even when AI gives good advice I still have to double check and confirm that the fixes actually work.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?
The way I decided whether a bug was really fixed was by using pytest and running a manual test as well. After I ran pytest and see that all four tests passed, I then tested the game manually in the Streamlit browser. This showed me that the core game logic was fixed and that the fixes did not break any existing test. It also showed me taht some user interface issues still remained, such as needing to click the Submit Guess button twice and habing issues with empty input handling. This taught me that passing automated tests does not always mean every part of the application works perfectly for the user. Yes, AI helped me understand the purpose of pytest tests and how they related to the game logic. It suggested running the test after making changes and explained what behavior the code should produce. I verified the results by running pytest and manually testing the game to make sure the fixes actually worked.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
I learned that Streamlit reruns the script from top to bottom every time the user interacts with the app, like when clicking a button. Session state is important because it keeps track of values like the secret number, score, and attempts so they do not reset every rerun. Without session state, the game would restart every time a guess was submitted. This helped me understand why some bugs happened when the state was not handled correctly. It's basically like saving progress each time when playing video games, without this feature you would have to start over every time.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
The habit or strategy that I would continue to use in future projects would be running pytest often after making each change. I would do this because it helps to ensure what I wanted to debug is working properly and that I did not break any other parts of the code. The thing I would do differently next time I work with AI on a coding task is to be more specific with my prompting and what I would want done. I learned as I communicated better the AI was able to help me better. This project really opened my eyes to how AI generates code because not only does it generate it, it tells you why and goes through each problem as if it is like thinking through the problem, just like we would as humans.