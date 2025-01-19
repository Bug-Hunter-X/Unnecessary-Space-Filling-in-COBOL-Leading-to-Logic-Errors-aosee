# Unnecessary Space Filling in COBOL Leading to Logic Errors

This repository demonstrates an uncommon bug in COBOL related to unnecessary space filling. The `MOVE SPACES` statement might lead to unexpected behavior if not used carefully.

## Bug Description

The COBOL code snippet initializes a variable named `WS-DATA` with spaces before a conditional statement. If the `WS-CONDITION` is not 'YES', `WS-OUTPUT` gets assigned 'VALUE2'. However, depending on the initial state of `WS-DATA` this might lead to unpredictable results. The unnecessary space filling can cause the comparison to fail, potentially leading to logic errors.

## How to Reproduce

1. Compile and run the provided COBOL code (`bug.cob`).
2. Observe the output.  Change the initial value of `WS-DATA` to see different behaviours.

## Solution

Review the usage of `MOVE SPACES`.  Consider if it is actually needed, or if the initial state of the variable is handled correctly and won't lead to unexpected comparisons. The ideal solution is to remove it if not strictly necessary.

## Additional Notes

This bug highlights the importance of careful variable initialization and understanding the implicit behavior of COBOL data structures.  Always carefully consider your initial values to avoid unexpected behaviour.  The solution file illustrates a cleaner and more reliable approach by removing the unnecessary `MOVE SPACES` statement.