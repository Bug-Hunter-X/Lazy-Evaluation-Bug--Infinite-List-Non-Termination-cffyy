# Haskell Lazy Evaluation Bug

This repository demonstrates a common error related to lazy evaluation in Haskell, specifically the issue of non-termination when working with infinite lists.  The `bug.hs` file contains code that attempts to print an infinite list, resulting in the program running indefinitely. The solution demonstrates how to correctly handle such cases.

## Bug Description

The problem arises from Haskell's lazy evaluation strategy.  The `infiniteList` is an infinite list, and printing it directly (`print infiniteList`) will cause the program to never terminate because it attempts to generate and print an infinite number of elements.  Even `print (take 10 infiniteList)` which seems to take only 10 elements is problematic, when you combine it with `print (infiniteList)` below, it will still result in non-termination. 

## Solution

The `bugSolution.hs` file provides a solution by demonstrating how to work with infinite lists safely, using `take` to limit the number of elements processed.