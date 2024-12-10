# Objective-C ARC and Weak Pointers: A Subtle Bug

This repository demonstrates a common, yet subtle, bug related to memory management in Objective-C when using Automatic Reference Counting (ARC) and weak pointers. The bug involves accessing a weak pointer after the object it references has been deallocated, leading to unexpected behavior and potential crashes.

## The Problem

When a weak pointer references an object that is deallocated, the weak pointer becomes nil. However, attempting to access the object through the weak pointer after it's deallocated can cause the application to crash or behave unpredictably. This is because the memory occupied by the object may have been reused by the system.

## Solution

The solution involves carefully checking if the weak pointer is nil before attempting to access the pointed-to object. This check prevents dereferencing a dangling pointer, ensuring that the application remains stable.

## How to Reproduce

1. Clone this repository.
2. Open the `bug.m` file to see the problematic code.
3. Open the `bugSolution.m` file to see the corrected code.
4. Compile and run both versions of the code to observe the difference in behavior.

This example highlights the importance of robust memory management practices in Objective-C, particularly when using weak pointers.