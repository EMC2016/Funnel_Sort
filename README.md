# Funnel Sort Algorithm - Cache-Oblivious Sorting in C

## Overview

This repository contains an implementation of the Funnel Sort algorithm, a cache-oblivious sorting algorithm designed to efficiently handle large data sets by minimizing cache misses. This implementation is inspired by the paper [*Cache-Oblivious Algorithms and Data Structures*](https://erikdemaine.org/papers/BRICS2002/paper.pdf) and is optimized for arrays of various sizes and types.

Funnel Sort is conceptually similar to merge sort, but with a crucial difference in how data is handled during the merging process. Instead of directly merging subarrays, Funnel Sort ensures that intermediate data is stored in a continuous memory space, which is calculated and managed before merging occurs. This deliberate memory management approach minimizes cache misses and significantly boosts performance, especially for large datasets.

In this implementation, Funnel Sort achieves better cache performance compared to traditional sorting algorithms like quicksort by reducing L1 cache misses by up to 3x, particularly for large arrays (e.g., 8 million elements). The algorithm is implemented in C for scalability, flexibility, and efficient memory usage.

## Features

- **Cache-Oblivious Design**: Funnel Sort minimizes cache misses without requiring explicit tuning for cache sizes.
- **Efficient Memory Usage**: Optimized to reduce L1 cache misses by up to 3x compared to quicksort.
- **Scalable**: Capable of sorting arrays of any size and type, making it highly flexible for various use cases.
- **Generic Implementation**: Supports arrays of different types (e.g., `unsigned long`, `int`, `float`).

## Implementation

The basic idea of Funnel Sort is similar to the concept described in [Funnelsort](https://en.wikipedia.org/wiki/Funnelsort). The key structures and functions in this implementation are as follows:

1. **Struct `buffer`**: Holds pointers to the input, intermediate, and output data.
  
2. **Struct `binary_merger`**: Connects multiple `buffers` to construct the funnel tree used for sorting.

3. **Functions `fill` and `merge_funnel`**: Recursively fill the funnel structure and merge data to produce the final sorted output.

4. **Function `recurfunnelbuild`**: Recursively builds the funnel tree by initializing the `buffer` and `binary_merger` structures.

5. **Function `ofunnelsort`**: The base case handles arrays of size ≤1000 using quicksort. For arrays larger than 1000 elements, Funnel Sort is applied. This function calls `recurfunnelbuild` to create the funnel structure and `fill` to generate the sorted output.

6. **Function `funnelsort`**: This is the main function that computes key parameters such as **N** (total size of the input array), **K** (number of initial funnels), and **d** (depth of the funnel tree). It also allocates memory for the intermediate buffers and initiates sorting by calling `ofunnelsort`.


## Performance

This implementation of Funnel Sort significantly improves cache efficiency, especially for large arrays. For instance, sorting an array of 8 million elements sees a substantial reduction in L1 cache misses when compared to traditional sorting algorithms like quicksort.

### Benchmarks

| Array Size      | Cache Miss Reduction (compared to quicksort) |
|-----------------|----------------------------------------------|
| 1,000,000       | 2.5x                                         |
| 8,000,000       | 3x                                           |
| 16,000,000      | 3x                                           |

## Customization

You can customize this implementation to sort arrays of different data types by modifying the type definitions in the code. For example, you can switch from `unsigned long` to `int` or `float` depending on your use case.



## Codes

All codes are in [this private repositary](https://github.com/EMC2016/funnelsort_codes.git). 
Please reach me emccs99@gmail.com for codes and more.

If you encounter any issues or have questions, please open an issue in this repository.