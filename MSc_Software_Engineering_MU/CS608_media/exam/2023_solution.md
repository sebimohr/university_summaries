# Software Testing - Exam Summer 2023

## Q1

### a

In regards to the test design time, exhaustive testing wouldn't be a problem,
as it wouldn't require too much code to exhaust the inputs for the `maxv()` method.

The problem is with the execution time.
As exhaustive testing tries to find find errors by testing all possible inputs,
it would have to test the method `maxv(...)` with array of the maximum size as well
as having elements that take each possible input, which would require and
infeasible amount of time.

### b

#### value line for t

INT.MIN_VALUE .. 0 | 1 .. 24 | 25 .. INT.MAX_VALUE

#### boolean expressions causes

1. t < 1
1. t < 25
1. isOn

#### boolean expressions effects

1. rv == HIGH
1. rv == LOW
1. rv == NONE

#### combination table (all)

| cause  | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- |
| t < 1  | 0   | 0   | 0   | 0   | 1   | 1   | 1   | 1   |
| t < 25 | 0   | 0   | 1   | 1   | 0   | 0   | 1   | 1   |
| isOn   | 0   | 1   | 0   | 1   | 0   | 1   | 0   | 1   |

#### combination table (feasible)

| cause  | 1   | 2   | 3   | 4   | 7   | 8   |
| ------ | --- | --- | --- | --- | --- | --- |
| t < 1  | 0   | 0   | 0   | 0   | 1   | 1   |
| t < 25 | 0   | 0   | 1   | 1   | 1   | 1   |
| isOn   | 0   | 1   | 0   | 1   | 0   | 1   |

#### decision table

| cause      | 1   | 2   | 3   | 4   | 7   | 8   |
| ---------- | --- | --- | --- | --- | --- | --- |
| t < 1      | 0   | 0   | 0   | 0   | 1   | 1   |
| t < 25     | 0   | 0   | 1   | 1   | 1   | 1   |
| isOn       | 0   | 1   | 0   | 1   | 0   | 1   |
| ---------- | --- | --- | --- | --- | --- | --- |
| rv == HIGH | 0   | 0   | 0   | 0   | 1   | 0   |
| rv == LOW  | 0   | 0   | 1   | 0   | 0   | 0   |
| rv == NONE | 1   | 1   | 0   | 1   | 0   | 1   |

#### confirmation

1. Rule 1: t >= 25 && isOn ==> NONE
1. Rule 2: !isOn ==> NONE
1. Rule 3: 1 <= t < 25 && isOn ==> LOW
1. Rule 4: !isOn ==> NONE
1. Rule 5: t < 1 && isOn ==> HIGH
1. Rule 6: !isOn ==> NONE

### c

<!-- TODO: TCI, TC and data values -->

## Q2

### a

#### i

Black Box testing: Errors in the general system implementation.

White Box testing: Errors in the detailed implementation.

#### ii

Black Box testing: As long as the in- and output stays the same, no impact.

White Box testing: Tests have to be rewritten, if the tested implementation is rewritten.

#### iii

Black Box testing: Yes, as soon as the interface is known.

White Box testing: No, as they require a look at the implementation.

#### iv

Black Box testing: The specification leads the test development.

White Box testing: The specification is important for the tests, but does not lead the test development itself.

#### v

Black Box testing: Yes, as they only test the general implementation of the interfaces, the coverage doesn't give a
fair overlook over the tests.

White Box testing: No. The coverage gives a detailed overview of which code parts still need to be tested.

### b

#### unexecuted statements

| id  | line number | condition        |
| --- | ----------- | ---------------- |
| 1   | 35          | mps < 0          |
| 2   | 49          | 107 <= mps < 138 |

1. first if condition (line 34) needs mps to be lower than 0
1. else if (line 48) executes when mps is greater or equal to 107 and lower than 138

#### TCI table

| TCI | line | Test case |
| --- | ---- | --------- |
| SC1 | 35   | T1.1      |
| SC2 | 49   | T1.2      |

#### TC table

| ID   | TCI  | INPUT = knots = mps / 5 | Expected Result |
| ---- | ---- | ----------------------- | --------------- |
| T1.1 | TCI1 | 0                       | ERROR           |
| T1.2 | TCI2 | 25                      | STRONG_BREEZE   |
