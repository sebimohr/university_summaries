# Rigorous Process - 2024 Summer

**Validation** is the proof, that a system meets its requirements.

**Verification** is the proof, that the program is working mathematically correct.

## Hoare Logic

Hoare Triple (Design by Contract):

- Precondition $\phi$
- Program S
- Postcondition $\psi$

Procedure:

- down-to-top: Postcondition must lead to precondition when executing all statements
- in loops:
  - **loop Guard** (Abbruchbedingung) must be true in loop, after loop $\neg$ guard must be true
  - **loop Invariant** is true:
    - before loop
    - begin of every loop execution
    - end of every loop execution
    - **only true when in loop**
- in if/else: every branch has a guard that holds in the branch itself

> Termination has to be proven!

## Topics to add

- Dafny
- Spin
