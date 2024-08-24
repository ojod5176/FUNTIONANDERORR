# SimpleContract

This is a basic Solidity smart contract that manages a single `uint256` value. The contract provides functions to set, increment, double, halve, check, and reset the value, with various safeguards in place using Solidity's `require()`, `assert()`, and `revert()` statements.

## Contract Overview

- **Contract Name**: `SimpleContract`
- **Solidity Version**: ^0.8.0

## State Variables

- `uint256 public value`: The stored value that can be manipulated through various functions in the contract.

## Functions

### 1. `setValue(uint256 newValue) public`

Sets a new value for the `value` variable, provided that the new value is greater than 0.

- **Parameters**:
  - `newValue`: The new value to be set.
- **Conditions**:
  - Requires `newValue` to be greater than 0.
- **Usage**:

    ```solidity
    contractInstance.setValue(5);
    ```

### 2. `checkValue() public view`

Checks if the current `value` is below 100. If not, the transaction will be reverted using `assert()`.

- **Conditions**:
  - Asserts that `value` is less than 100.
- **Usage**:

    ```solidity
    contractInstance.checkValue();
    ```

### 3. `resetValue() public`

Resets the `value` to 0, but only if it’s not already 0. If `value` is already 0, the transaction will be reverted.

- **Conditions**:
  - Reverts if `value` is already 0.
- **Usage**:

    ```solidity
    contractInstance.resetValue();
    ```

### 4. `increment() public`

Increments the `value` by 1, but only if the current `value` is less than 10.

- **Conditions**:
  - Requires `value` to be less than 10.
- **Usage**:

    ```solidity
    contractInstance.increment();
    ```

### 5. `doubleValue() public`

Doubles the `value`, but reverts if the result would exceed 200.

- **Conditions**:
  - Reverts if the doubled value would exceed 200.
- **Usage**:

    ```solidity
    contractInstance.doubleValue();
    ```

### 6. `halveValue() public`

Halves the `value`, but only if the current `value` is greater than 1.

- **Conditions**:
  - Requires `value` to be greater than 1.
- **Usage**:

    ```solidity
    contractInstance.halveValue();
    ```

## Example Usage

Here’s an example of how to interact with the `SimpleContract`:

```solidity
contractInstance.setValue(10);     // Sets the value to 10
contractInstance.increment();      // Increments the value to 11
contractInstance.doubleValue();    // Doubles the value to 22
contractInstance.halveValue();     // Halves the value to 11
contractInstance.checkValue();     // Asserts that the value is less than 100
contractInstance.resetValue();     // Resets the value to 0

