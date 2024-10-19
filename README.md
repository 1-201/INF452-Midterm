# INF452-Midterm

## Description
The Essay Checker allows users to input their essays to obtain word and character counts, estimate reading time, and apply automatic corrections to enhance sentence capitalization. Unlike existing word counters, this program lets users choose which statistics they want to see and automatically capitalizes the beginning of each sentence.

## Features
1. **Word Count**: Counts the total number of words in the essay.
2. **Character Count**: Counts the total number of characters in the essay.
3. **Reading Time**: Estimates the average reading time
4. **Correction**: Automatically capitalizes the first letter of each sentence after a period.

## Considerations
1. The reading time is based on an average reading speed of 275 words per minute.
* Source: https://wordcounter.net/
2. Sentences are split based on the presence of a period followed by a space.
   * This may not account for all sentence-ending scenarios.
     * Examples of Scenarios Not Accounted For:
       * Example 1: Abbreviations
         <code>Fruits (e.g. Apples)</code>
       * Example 2: Decimal Points
         <code>The temperature was 23.5 degrees. It was a warm day.</code>

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









