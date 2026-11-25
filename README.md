# Parallel List Signal Drift

The lesson slides for this assessment can be found [here](https://smugpumpkins.github.io/learn-cs/lessons/cse2120/parallel-lists/#/slide-1).

## Basic Premise

You will be provided with two **parallel lists** containing signal readings:

- `expected` contains the values that were expected.
- `received` contains the values that were actually received.

Values stored at the same index belong together. For example, `expected[3]` should always be compared with `received[3]`.

Your task is to process the two lists together and calculate how much each received value differs from its expected value.

The **drift** of a reading is its absolute difference:

```text
absolute_drift = abs(expected_value - received_value)
```

Your program should create a new list containing the drift for every pair of readings and then analyze the complete dataset.

## Basic File Structure

Your starter folder will contain:

```text
basic/
└── main.py
```

The `expected` and `received` lists will already be provided inside `main.py`.

## Basic Requirements

* [ ] Traverse the `expected` and `received` lists together so values at matching indices are processed as a pair.
* [ ] Calculate the **absolute difference** between each expected value and its corresponding received value.
* [ ] Store every calculated difference in a new list named `drift`.
* [ ] Display every reading in a clearly formatted way that shows the **expected value**, **received value**, and **absolute drift** for that position.
* [ ] Calculate and display the **total drift** by adding together every value in the `drift` list.
* [ ] Calculate and display the **average drift** of all readings.

Your displayed data could use a format similar to:

*(You will have more than 2 items in eachlist, this is just an example).*

```text
Expected: 9
Received: 11
Drift:    2

Expected: 8
Received: 14
Drift:    6

Total Drift: 8
Average Drift: 4.0
```

> Fully completing the Basic Requirements earns **16/20 marks, or 80%**.

## Basic Assessment — 16 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| Parallel List Traversal | Correctly traverses the two lists so matching indices are processed together. | 3 |
| Drift Calculation | Correctly calculates the absolute difference between every pair of expected and received values. | 3 |
| Drift List | Creates a new list containing the correctly calculated drift for every position. | 3 |
| Formatted Data Display | Clearly displays the expected, received, and drift values together for every position. | 3 |
| Total Drift | Correctly calculates and displays the sum of all drift values. | 2 |
| Average Drift | Correctly calculates and displays the average of all drift values. | 2 |
|  | **Total** | **16** |

## Advanced Premise

Extend your Basic Signal Drift Analyzer so that it provides more information about the **direction** and **quality** of the signal drift.

A reading has:

- **Positive drift** when the received value is greater than the expected value.
- **Negative drift** when the received value is less than the expected value.
- **No directional drift** when the two values are equal.

The user will also define two thresholds that determine signal quality. Your program must ask for an **excellent** signal threshold, and an **acceptable** signal threshold. The program must also prevent the **acceptable** threshold from being less than the **excellent** threshold.

For example, if the user enters:

```text
Excellent Signal Threshold: 2
Acceptable Signal Threshold: 5
```

then the program should classify absolute drift as:

```text
0–2     → Excellent
3–5     → Acceptable
Above 5 → Poor
```

The exact thresholds should come from the user.

## Advanced File Structure

Your starter folder will contain:

```text
advanced/
└── main.py
```

You can begin by copying your completed Basic program into this file.

## Advanced Requirements

* [ ] Compare the original `expected` and `received` values and count how many readings have **positive drift** and how many have **negative drift**. Display both counts.
* [ ] Use `input()` to ask the user for an **Excellent Signal Threshold** and an **Acceptable Signal Threshold**.
* [ ] Validate the thresholds so that the Excellent threshold cannot be greater than the Acceptable threshold. Invalid values must be rejected and entered again.
* [ ] Use the thresholds and the absolute values in the `drift` list to count how many readings are **Excellent**, **Acceptable**, and **Poor**, then clearly display all three counts.
* [ ] Validate numeric input and handle incorrect input without crashing the program.

## Advanced Assessment — 4 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| Drift Direction | Correctly counts and displays readings with positive and negative drift. | 1 |
| Threshold Input | Collects valid Excellent and Acceptable thresholds and prevents the Excellent threshold from being greater than the Acceptable threshold. | 1 |
| Signal Classification | Correctly classifies and counts all readings as Excellent, Acceptable, or Poor using the user-provided thresholds. | 1 |
| Input Validation and Error Handling | Prevents invalid numeric input from crashing the program and allows the user to correct invalid values. | 1 |
|  | **Total** | **4** |
