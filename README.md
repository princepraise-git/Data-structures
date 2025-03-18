# Data-structures
# Vector Operations in JavaScript

This repository contains JavaScript implementations for two vector-related problems: calculating the sum of distinct elements from two sets and determining the dot product and orthogonality of vectors.

## Table of Contents

- [Problem 1: Sum of Distinct Elements](#problem-1-sum-of-distinct-elements)
- [Problem 2: Dot Product and Orthogonality Check](#problem-2-dot-product-and-orthogonality-check)
- [Usage](#usage)
- [Examples](#examples)
- [Installation](#installation)
- [License](#license)

## Problem 1: Sum of Distinct Elements

### Description
Given two sets of elements, this function calculates the sum of all distinct elements that are present in either set. The goal is to identify elements that are unique to each set and sum them up.

### Algorithm Steps:
1. Initialize a variable `sum` to 0.
2. For each element in the first set, check if it exists in the second set. If it does not, add it to the `sum`.
3. Repeat the same process for the second set.
4. Return the final value of `sum`.

### Implementation
```javascript
function sumOfDistinctElements(set1, set2) {
    let sum = 0;

    function addDistinctElements(sourceSet, targetSet) {
        for (let i = 0; i < sourceSet.length; i++) {
            const element = sourceSet[i];
            if (!targetSet.includes(element)) {
                sum += element; // Add to sum if distinct
            }
        }
    }

    addDistinctElements(set1, set2);
    addDistinctElements(set2, set1);
    
    return sum;
}
