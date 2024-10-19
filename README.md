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
*  This may not account for all sentence-ending scenarios (e.g. abbreviations)
  *  Examples of Scenarios Not Accounted For

