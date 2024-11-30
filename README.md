
# ADS Resolution
**Resolution of a College Assignment in C**

## Description
The initial code provided by the university introduces various features and challenges related to a voting system written in C. Below are the primary issues identified in the original code, along with the solutions implemented to address them:

### 1. Candidate Number Validation
When an invalid candidate number was entered, the system failed to display the message `"Invalid candidate number!"`. The validation logic needed adjustments.

### 2. Vote Counting
The vote tallying function was incorrectly displaying the vote count for each candidate.

### 3. Vote Percentage Calculation
The option to display the percentage of votes for each candidate produced incorrect results, as the calculations were not being performed accurately.

### 4. Menu Functionality
The menu exhibited unintended behavior where selecting an option (1, 2, or 3) also executed subsequent options in sequence.

---

## Responses to Issues

### 1. **Candidate Number Validation**
The message `"Invalid candidate number"` was not being displayed due to a logic issue in a loop structure. When selecting the vote option, the program enters the `votar` method, which contains a `for` loop that needed correction.

- The `encontrado` variable is initialized with the value `0` and is set to `1` only when the entered candidate number matches a valid number in the candidate list. However, if the number is invalid, the `encontrado` variable remains `0`.
- To fix this, the `if(encontrado)` statement on line 21 was updated to `if(!encontrado)` or `if(encontrado == 0)`.

This adjustment ensures that the message `"Invalid candidate number!"` is displayed when the entered number is invalid.

### 2. **Vote Tallying**
The vote tallying function was displaying incorrect totals because the `for` loop in the `apurarVotos` method was initialized with `int i = 1`, causing the first candidate to be skipped.

- The fix was to initialize `int i = 0`, ensuring the loop iterates through all candidates without skipping the first one.

### 3. **Vote Percentage Calculation**
The logic in the `percentualVotos` method for calculating vote percentages was incorrect. The variable `percentual` was not properly calculating the percentage for each candidate.

- The fixed logic calculates the percentage correctly by iterating through all candidates, accessing their vote count, multiplying by `100`, and dividing by the total votes. The corrected line is:
  ```c
  float percentual = (candidatos[i].votos * 100) / totalVotos;
  4. Menu Functionality
The menu options were being displayed repeatedly due to the absence of a break statement at the end of each case in the switch structure.

4. Menu Functionality
The menu options were being displayed repeatedly due to the absence of a break statement at the end of each case in the switch structure.

Adding the break statements ensures that only the selected option is executed, and subsequent cases do not run unintentionally.

Adding the break statements ensures that only the selected option is executed, and subsequent cases do not run unintentionally.
Corrected Code
The corrected code for the voting system is available in this repository.


