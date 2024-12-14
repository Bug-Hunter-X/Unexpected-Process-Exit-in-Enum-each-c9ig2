# Elixir Enum.each and Process.exit

This repository demonstrates a subtle but potentially problematic issue when using `Process.exit` within an `Enum.each` loop in Elixir.  The example code shows how prematurely terminating the loop using `Process.exit` can lead to unexpected behavior and data loss.  The solution provides an alternative approach using a conditional return or a different enumeration method to handle the termination gracefully.

## Bug Report
The `bug.exs` file contains code that uses `Process.exit` within `Enum.each`. When the condition `x == 3` is met the process is terminated before all elements in list are processed. This is typically undesirable, especially in larger concurrent applications where an unforeseen premature exit can cause significant problems.