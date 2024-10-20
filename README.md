# INF452-Midterm

## Description
The Essay Checker allows users to input their essays to obtain word and character counts, estimate reading time, and apply automatic corrections to enhance sentence capitalization. Unlike existing word counters, this program lets users choose which statistics they want to see and automatically capitalizes the beginning of each sentence.

## Features
1. **Word Count**: Counts the total number of words in the essay.
2. **Character Count**: Counts the total number of characters in the essay.
3. **Reading Time**: Estimates the average reading time
4. **Correction**: Automatically capitalizes the first letter of each sentence after a period.

## Rules
1. Input Format: The user should input a single block of text. Multi-paragraph essays should be entered as continuous text, with each sentence separated by a period followed by a space.
2. Sentence Structure: The program expects sentences to end with a period followed by a space. Other punctuation marks (e.g. question marks, exclamation points) may not be properly accounted for in sentence separation.
3. Sentence Handling Limitations: Sentences are split based on the presence of a period followed by a space.
    * This may not account for all sentence-ending scenarios.
     * Examples of Scenarios Not Accounted For:
       * Example 1: Abbreviations e.g. Fruits (e.g. Apples)
       * Example 2: Decimal Points e.g. The temperature was 23.5 degrees. It was a warm day.
4. The code preserves the original spacing in the sentences.
   * If you want to remove leading and trailing whitespace from each sentence, add the following line in line 29:
     ```python
     sentence = sentence.strip()  # Remove leading/trailing whitespace
     ```
   * After adding this line, an input like:
     ```plaintext
     This is a sentence.     That has a lot of space.
     ```
     *will turn into*:
     ```plaintext
     This is a sentence. That has a lot of space.
     ```
5. Exit Conditions: The program will exit if the user types <code>no</code> when asked if they want to check another essay or if they select the exit option <code/>6</code> from the choice.
   
## Considerations
1. The reading time is based on an average reading speed of 275 words per minute.
* Source: https://wordcounter.net/
2. Sentences are split based on the presence of a period followed by a space, which may not account for all cases.

## Code Structure
The program uses two main loops:
1. Outer Loop:
* This loop allows the program to run multiple times, enabling users to check different essays without restarting. It continues until the user decides to exit by typing <code>no</code>
2. Inner Loop:
* This loop handles user input for selecting which statistics to display. It prompts the user for a choice (e.g. all, word count, character count, reading time, corrected essay, exit) and displays the corresponding information based on that choice. This loop continues until the user decides to exit by typing <code>6</code>

## How it works
1. **Input**: The user inputs their essay as a single block text.
2. **Processing**: The program calculates:
* Word count
* Character count
* Reading time
* Corrected essay with capitalized sentences
3. **Output**: The user can choose which option to view or exit the program.


## Instruction
1. Inputting the Essay:
* The program prompts the user to enter their essay:
  ```python
  Please enter your essay:
  ```
* The user inputs:
  ```python
  The quick brown fox jumps over the lazy dog. this sentence needs correction.
  ```
2. Program Processes the Input:
* The program calculates:
   * Word count: 13
   * Character count: 76
   * Reading time: 3 sec
   * Corrected essay: The quick brown fox jumps over the lazy dog. This sentence needs correction.
3. Choosing Output Options:
* The program displays options for the user:
```python
What information would you like to see?
1. All
2. Word count
3. Character count
4. Reading time
5. Corrected essay
6. Exit
```
* The user selects an option by entering a number, for example, if the user selects <code>2</code>
```python
Word count: 13
```
4. Continuing or Exiting:
* The program continues to loop through these options until the user selects option 6 to exit.
* If the user selects <code>6</code>, the program asks if the user wants to check another essay:
```python
Do you want to check another essay? (yes/no): 
```
* If the user types <code>yes</code>, the program returns to the essay input prompt.
If the user types <code>no</code>, the program will print:
```python
Thank you for using the Essay Checker!
```









