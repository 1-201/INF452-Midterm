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
       * Example 1: Abbreviations
         <code>Fruits (e.g. Apples)</code>
       * Example 2: Decimal Points
         <code>The temperature was 23.5 degrees. It was a warm day.</code>
4. Exit Conditions: The program will exit if the user types <code>no</code> when asked if they want to check another essay or if they select the exit option <code/>6</code> from the choice.
   
## Considerations
1. The reading time is based on an average reading speed of 275 words per minute.
* Source: https://wordcounter.net/

## Execution
1. **Input**: The user inputs their essay as a single block text.
2. **Processing**: The program calculates word count and character count, reading time, and corrects sentence capitalization.
3. **Output**: The user can choose which option to view or exit the program.

## Code Structure
The program uses two main loops:
1. Outer Loop:
* This loop allows the program to run multiple times, enabling users to check different essays without restarting. It continues until the user decides to exit by typing <code>no</code>
2. Inner Loop:
* This loop handles user input for selecting which statistics to display. It prompts the user for a choice (e.g. all, word count, character count, reading time, corrected essay, exit) and displays the corresponding information based on that choice. This loop continues until the user decides to exit by typing <code>6</code>









