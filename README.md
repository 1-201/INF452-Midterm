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
4. The code removes leading and trailing whitespace from the sentences
   * If you want to preserve the original spacing in the sentences, remove line 41:
     ```python
        sentence = sentence.strip()  # Remove leading/trailing whitespace
     ```
   * An input like:
     ```plaintext
     This is a sentence.     that has a lot of space.
     ```
   * will turn into:
     ```plaintext
     This is a sentence. That has a lot of space.
     ```
5. Capitalization Behaviour: Sentences are split based on the presence of a period followed by a space.
   * For instance, when the input is:
     ```plaintext
     This is a sentence...   that has a lot of space.
     ```
   * The output will be:
     ```plaintext
     This is a sentence... That has a lot of space.
   * Conversely, with an input that has extra spaces before a period:
     ```plaintext
     This is a sentence  ...that has a lot of space.
     ```
   * The output will remain:
     ```plaintext
     This is a sentence  ...that has a lot of space.
     ```
   * In this case, the input is not split into separate sentences due to the absence of a period followed by a space, resulting in the first word "that" not being capitalized.
6. Exit Conditions: The program will exit if the user types <code>no</code> when asked if they want to check another essay or if they select the exit option <code/>6</code> from the choice.
   
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
     ```plaintext
     Please enter your essay:
     ```
   * The user inputs:
     ```plaintext
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
      ```plaintext
      What information would you like to see?
      1. All
      2. Word count
      3. Character count
      4. Reading time
      5. Corrected essay
      6. Exit
      ```
   * The user selects an option by entering a number, for example, if the user selects <code>2</code>
      ```plaintext
      Word count: 13
      ```
4. Continuing or Exiting:
   * The program continues to loop through these options until the user selects option 6 to exit.
   * If the user selects <code>6</code>, the program asks if the user wants to check another essay:
      ```plaintext
      Do you want to check another essay? (yes/no): 
      ```
   * If the user types <code>yes</code>, the program returns to the essay input prompt.
   * If the user types <code>no</code>, the program will print:
      ```plaintext
      Thank you for using the Essay Checker!
      ```

## Example Run
1. Example Run 1
   * Input:
      ```plaintext
      This is a sample essay. it includes some sentences.
      ```
   * Output:
      ```plaintext
      What information would you like to see?
      1. All
      2. Word count
      3. Character count
      4. Reading time
      5. Corrected essay
      6. Exit
      Enter your choice (1-6): 2
      Word count: 9
      Enter your choice (1-6): 3
      Character count: 51
      Enter your choice (1-6): 4
      Reading time: 2 sec
      Enter your choice (1-6): 5
      Corrected essay: This is a sample essay. It includes some sentences.
      ```

2. Example Run 2
   * Input
      ```plaintext
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ac orci libero. Vestibulum sed porta odio. Integer finibus augue ut elit euismod, et tristique diam congue. Proin ultricies mauris a mauris imperdiet efficitur. Nullam at rutrum justo, vitae tempor nisl. Quisque eget eleifend lacus. In eu lectus sit amet purus maximus ultrices. Ut lacinia imperdiet ligula vel efficitur. Donec tincidunt erat dui, et tristique lacus semper ac. Nullam justo massa, tincidunt ut neque a, porta tristique sem. Sed sagittis sodales dolor a semper. Integer finibus suscipit felis, ac scelerisque nulla. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse sed ipsum eget sapien semper aliquam. Nam hendrerit justo elit, varius porttitor elit viverra eu. Donec tristique, velit eget consectetur viverra, lectus ex accumsan lectus, quis pharetra mauris urna non ipsum. Morbi vehicula rutrum vehicula. Quisque turpis quam, venenatis vel condimentum vel, mattis non nisi. Curabitur non lorem in ante vulputate gravida ut at nisl. Etiam quis tempor mi. Proin vel vulputate libero. Nam erat lectus, pretium quis justo tincidunt, iaculis sodales mauris. Sed pulvinar velit vel mauris gravida egestas. Nulla ac ante elit. Donec sed odio at massa venenatis ultricies non in neque. Vivamus in justo consequat massa congue luctus. Praesent mollis orci ac risus aliquet, bibendum bibendum sem sollicitudin. Aliquam erat volutpat. Nulla facilisi. Donec malesuada eu lacus at euismod. Duis gravida lacus ut ante bibendum, eget porta ex dapibus. Ut at turpis tristique, scelerisque enim non, ultricies libero. Cras ullamcorper feugiat sapien ut sagittis. Cras id risus ac lacus hendrerit semper. Aliquam vitae urna at nisl imperdiet porta blandit vel neque. Cras in mauris aliquet, ultrices sapien sit amet, semper justo. Curabitur ultrices dapibus ipsum, non maximus eros eleifend et. Proin non dui enim. Nunc tristique consequat est sed dictum. Mauris molestie ex ut augue varius, in scelerisque purus suscipit. Sed semper fringilla nibh vel mattis.
      ```
   * Output:
      ```plaintext
      What information would you like to see?
      1. All
      2. Word count
      3. Character count
      4. Reading time
      5. Corrected essay
      6. Exit
      Enter your choice (1-6): 2
      Word count: 308
      Enter your choice (1-6): 3
      Character count: 2045
      Enter your choice (1-6): 4
      Reading time: 1 min 7 sec
      ```









