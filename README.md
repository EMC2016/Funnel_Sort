# Funnel Sort Algorithm - Cache-Oblivious Sorting in C

## Overview

This repository contains an implementation of the **Funnel Sort** algorithm, a cache-oblivious sorting algorithm designed to efficiently handle large data sets by minimizing cache misses. This implementation is inspired by the paper *Cache-Oblivious Algorithms and Data Structures* and is optimized for arrays of various sizes and types.

Funnel Sort achieves better cache performance compared to traditional sorting algorithms like quicksort by reducing L1 cache misses by up to 3x, particularly for large arrays (e.g., 8 million elements). The algorithm is implemented in C for scalability, flexibility, and efficient memory usage.

## Features

- **Cache-Oblivious Design**: Funnel Sort minimizes cache misses without requiring explicit tuning for cache sizes.
- **Efficient Memory Usage**: Optimized to reduce L1 cache misses by up to 3x compared to quicksort.
- **Scalable**: Capable of sorting arrays of any size and type, making it highly flexible for various use cases.
- **Generic Implementation**: Supports arrays of different types (e.g., `unsigned long`, `int`, `float`).


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

## Contribution

Feel free to fork the repository and contribute to the project! Here are some areas that could be improved:
- **Performance Tuning**: Further optimization for specific hardware architectures.
- **Parallelization**: Implementing multi-threading for improved performance on large datasets.
- **Unit Testing**: Adding unit tests to ensure the accuracy and performance of the algorithm.

## Codes

All codes are in [this private repositary](https://github.com/EMC2016/funnelsort_codes.git). 
Please reach me emccs99@gmail.com for codes and more.

If you encounter any issues or have questions, please open an issue in this repository.