# Quiz-App

This Python application implements a simple quiz game with a graphical user interface (GUI). Users are presented with questions and can select "True" or "False" as answers. The application tracks the user's score and provides feedback on their responses.

## Project Structure

The project consists of the following files:

* **main.py**: The main entry point of the application, responsible for initializing the quiz and starting the GUI.
* **question_model.py**: Defines the `Question` class, representing a single quiz question with its text and correct answer.
* **data.py**: Contains the `question_data` list, a list of dictionaries, where each dictionary represents a question and its answer.
* **quiz_brain.py**: Implements the `QuizBrain` class, which manages the quiz logic, including question navigation, answer checking, and score keeping.
* **ui.py**: Defines the `QuizInterface` class, responsible for creating and managing the GUI elements of the quiz.

## How it Works

1. **Initialization (main.py):**
   - The `question_data` is loaded from `data.py`.
   - A list of `Question` objects is created using the data, forming the `question_bank`.
   - A `QuizBrain` object is initialized with the `question_bank`.
   - A `QuizInterface` object is created, passing the `QuizBrain` as an argument. This sets up the GUI.

2. **Question Display (ui.py):**
   - The `QuizInterface` displays the current question from the `QuizBrain`.
   - Buttons for "True" and "False" are presented to the user.

3. **Answer Checking (quiz_brain.py):**
   - When the user clicks a button, the `QuizInterface` calls the `check_answer` method of the `QuizBrain`.
   - `check_answer` compares the user's answer with the correct answer and updates the score.
   - Feedback is provided to the user (e.g., indicating if the answer was correct or incorrect).

4. **Question Progression (quiz_brain.py and ui.py):**
   - The `QuizBrain` keeps track of the current question number.
   - After each answer, the `QuizBrain` moves to the next question.
   - The `QuizInterface` updates the displayed question and provides visual feedback on the progress.

5. **Game Completion (main.py):**
   - The commented-out section in `main.py` (the `while` loop) would have allowed the quiz to be played in the console, but it is not currently used.
   - After the GUI is closed, the final score is printed in the console (this is still executed).

## Key Classes and their Responsibilities

### question_model.py: Question Class

- **Attributes:**
    - `text`: The text of the question (string).
    - `answer`: The correct answer to the question (string, "True" or "False").

### data.py: question_data

- A list of dictionaries, where each dictionary has:
    - `"question"`: The text of a quiz question (string).
    - `"correct_answer"`: The correct answer to the question (string, "True" or "False").

### quiz_brain.py: QuizBrain Class

- **Attributes:**
    - `question_number`: The index of the current question in the `question_list` (integer, starts at 0).
    - `score`: The user's current score (integer, starts at 0).
    - `question_list`: A list of `Question` objects.
- **Methods:**
    - `next_question()`: Returns the next `Question` object in the list.
    - `still_has_questions()`: Checks if there are more questions remaining (boolean).
    - `check_answer(user_answer, correct_answer)`: Compares the user's answer with the correct answer, updates the score, and provides feedback.

### ui.py: QuizInterface Class

- **Attributes:**
    - `quiz`: A `QuizBrain` object.
    - GUI elements (e.g., labels, buttons) to display the question and answer options.
- **Methods:**
    - `get_next_question()`: Updates the GUI with the next question and resets button states.
    - `true_pressed()`: Handles the "True" button click, checks the answer, and updates the GUI.
    - `false_pressed()`: Handles the "False" button click, checks the answer, and updates the GUI.

## Further Development

- Implement the `while` loop in `main.py` to enable console-based gameplay.
- Enhance the GUI with features like progress bars, timers, and more visually appealing elements.
- Add more questions to the `question_data` to expand the quiz content.
- Implement different question types (e.g., multiple choice, fill in the blanks).
- Store high scores and provide a way for users to track their progress.
- Add error handling and input validation.

## Screenshots

![image](https://github.com/user-attachments/assets/119ceffd-5dff-4980-af83-2d25d7fcaa73)
![image](https://github.com/user-attachments/assets/8dfd251d-417b-4d6f-8587-9e4bd7e609dd)
![image](https://github.com/user-attachments/assets/2eac6fc2-ba43-4573-ae2f-545470443178)
![image](https://github.com/user-attachments/assets/669668b7-134a-4112-8ed3-76bb1807598f)


This readme provides a comprehensive overview of the quiz game application. By understanding the code structure and the responsibilities of each class, you can further develop and enhance the application.
