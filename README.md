# VHDL Counter Overflow Bug and Solution

This repository demonstrates a common VHDL coding error: integer overflow in a counter. The `buggy_counter.vhdl` file contains a counter that increments without bound. This can lead to unexpected simulation results or even hardware malfunctions if synthesized.

The `fixed_counter.vhdl` file provides a corrected version using a saturated counter to prevent overflow.

## Bug Description
The original counter uses the `integer` type, which has an unbounded range.  When the counter reaches its maximum value, it wraps around to its minimum, leading to incorrect counting.

## Solution
The solution employs a saturated counter, which stops incrementing once it reaches a predefined maximum value. This ensures correct operation and prevents unpredictable behavior.  Alternatively, using `unsigned` with a defined range is another effective solution. 

## How to reproduce the bug
1. Simulate `buggy_counter.vhdl` using a VHDL simulator (e.g., ModelSim, GHDL).
2. Observe the counter's behavior over a long simulation time. You will notice it eventually wraps around.

## How to test the solution
1. Simulate `fixed_counter.vhdl` using a VHDL simulator.
2. Verify that the counter stops incrementing at the defined maximum value.
