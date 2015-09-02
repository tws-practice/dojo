The 24 Game tests one's mental arithmetic.
Write a program that randomly chooses and displays four digits, each from one to nine, with repetitions allowed. 
The program should prompt for the player to enter an arithmetic expression using just those, and all of those four digits, used exactly once each. 
The program should check then evaluate the expression. The goal is for the player to enter an expression that evaluates to 24.

- Only multiplication, division, addition, and subtraction operators/functions are allowed.
- Division should use floating point or rational arithmetic, etc, to preserve remainders.
- Brackets are allowed, if using an infix expression evaluator.
- Forming multiple digit numbers from the supplied digits is disallowed. (So an answer of 12+12 when given 1, 2, 2, and 1 is wrong).
- The order of the digits when given does not have to be preserved.

## Note:
The type of expression evaluator used is not mandated. An [RPN](https://en.wikipedia.org/wiki/Reverse_Polish_notation) evaluator is equally acceptable for example.
The task is not for the program to generate the expression, or test whether an expression is even possible.
