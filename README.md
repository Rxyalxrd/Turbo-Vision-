# Input integer number

## Overview

`IntInput` is a Turbo Vision module that provides a custom input field for integer values with specified ranges. It extends the standard input line component to validate and handle integer input, ensuring the values fall within defined intervals.

## Components

### Types

- **Interval**: An enumerated type representing the range intervals:
  - `a_b`: [min, max]
  - `a_inf`: [min, ∞)
  - `inf_b`: (-∞, max]
  - `inf_inf`: (-∞, ∞)

### TInputInt Object

- **Fields**:
  - `min`: The minimum value of the range.
  - `max`: The maximum value of the range.
  - `int`: The type of interval.

- **Constructor**:
  - `Init(R: TRect; i: integer; mina, maxa: longint)`: Initializes the input line with specified rectangle `R`, max length `i`, minimum value `mina`, and maximum value `maxa`.

- **Methods**:
  - `DataSize: word`: Returns the size of the data.
  - `GetData(var Rec)`: Retrieves the integer data from the input field.
  - `SetData(var Rec)`: Sets the input field with the provided integer data.
  - `Valid(com: word): boolean`: Validates the input data against the defined range.

## Example Application: IntegerInput

The `IntegerInput` program demonstrates the usage of the `TInputInt` object. It presents a dialog to the user for entering an integer within the specified range of -100 to 100.

### TMyApp Object

- **Methods**:
  - `Run`: Executes the main functionality by showing the integer input dialog.
  - `HandleEvent(var Event: TEvent)`: Handles application events, triggering the integer input dialog on a new command.
  - `ShowDateDialog`: Displays the dialog for entering an integer.

### Main Program

- Initializes and runs an instance of `TMyApp`, showing the dialog for integer input and validating the input against the specified range.

## Usage

1. **Integration**:
   - Include `IntInput` in your uses clause.
   - Create an instance of `TInputInt` and initialize it with the desired range.
   - Use `GetData` and `SetData` to interact with the input value.
   - Ensure `Valid` is called to validate the input.

2. **Example**:
   - The provided example in `IntegerInput` shows a dialog for inputting an integer within the range of -100 to 100.

## Error Handling

- Displays error messages for invalid inputs, such as non-integer values or values outside the specified range, using message boxes.

## Dependencies

- The module depends on standard Pascal units such as `Objects`, `Views`, `Dialogs`, and `MsgBox`.
