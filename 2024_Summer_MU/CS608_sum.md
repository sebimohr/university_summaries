# Software Testing - Summer 2024

## Software Testing Process

### Steps

1. **Analysis**: Analyze specification and software implementation
1. **Identify Test Coverage Items**: Criteria the tests address
1. **Identify Test Cases**: Specify data required to address test coverage items (TCI)
1. **Test Design Verification**: Review test cases to ensure every TCI has been covered
1. **Test Implementation**: Implement using test tool library
1. **Test Execution**: Execute tests using selected input data values
1. **Review Test Results**: Examine test results for failures

### Test Cases Template

| ID  | TCI  | Inputs (multiple columns) | Expected Results (return value) |
| --- | ---- | ------------------------- | ------------------------------- |
| ID  | List | Values                    | Values                          |

> For error values the ID and the error value get marked with a \*

## Black Box Testing

Testing for specification: does the tested code generate correct results?

### Equivalence Partitions

1. **Analysis**: Identify natural ranges & specification-based ranges
   (Specification-based ranges declare which range changes the result)
1. **Identify Test Coverage Items**: TCI for each partition of each input / output parameter
1. **Equivalence Value for each TCI**: Identify middle value of short ranges or convenient value for long ranges
1. **Identify Test Cases**: Select first uncovered TCI,
   indicate [duplicates] when all TCIs of input are covered or result is already covered,
   last Test Cases cover error partitions, indicated with \*
1. **Test Design Verification**: Check if all TCIs are covered

#### Examples

![TCI Table](CS608_media/EP_TCI.png)

![TC Table](CS608_media/EP_TC.png)

### Boundary Value Analysis

1. **Analysis**: Same as with EPs
1. **Identify Test Coverage Items**: Each TCI covers one boundary value (min or max)
1. **Identify Test Cases**: Same as with EPs

#### Examples

![TCI Table](CS608_media/BVA_TCI.png)

![TC Table](CS608_media/BVA_TC.png)

### Decision Table

<!-- TODO: Week 4 -->

## White Box Testing

Testing the implementation: do valid results get generated when executed?

### SC

### BC

## Object Oriented Testing

## Application Testing

## Test Automation

## Random testing

A large number of inputs gets selected randomly, approximates to exhausive testing.

- Exercises program, demonstratest that it does not crahs
- Poor distribution of inputs, as it doesn't respect partitions
- Can't tell if results are correct -> too many test

1. **Analysis**:
1. **Identify Test Coverage Items**:
1. **Identify Test Cases**:
1. **Test Design Verification**:
1. **Test Implementation**:
1. **Test Execution**:
1. **Review Test Results**:
