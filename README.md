# Parallel Minimum Finder

## Overview

This repository contains the parallel implementation of finding the minimum value in a very large array using different parallel computing techniques, including OpenMP, POSIX threads, and SIMD (Single Instruction, Multiple Data). The project demonstrates how parallelism can significantly improve the performance of basic algorithms.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Implementation Details](#implementation-details)
   - [OpenMP](#openmp)
   - [POSIX](#posix)
   - [SIMD](#simd)
4. [Results](#results)
5. [Usage](#usage)
6. [License](#license)

## Introduction

This project demonstrates the implementation of a parallel algorithm to find the minimum value in a large array. The implementation uses three different parallel computing techniques: OpenMP, POSIX threads, and SIMD instructions. Each technique showcases the performance improvements that can be achieved through parallelism.

## Project Structure

The project is organized into three main directories, each containing the implementation of the algorithm using a different parallel computing technique:

- `OpenMP/`: Contains the implementation using OpenMP.
- `POSIX/`: Contains the implementation using POSIX threads.
- `SIMD/`: Contains the implementation using SIMD instructions.

Each directory contains a `main.cpp` file with the implementation.

## Implementation Details

### OpenMP

The OpenMP implementation uses the `#pragma omp parallel` directive to parallelize the computation of the minimum value in the array. The code initializes the array, computes the minimum value serially for comparison, and then computes the minimum value in parallel.

**File:** `OpenMP/main.cpp`

### POSIX

The POSIX implementation uses `pthread` to create multiple threads, each responsible for computing the local minimum in a segment of the array. A mutex is used to ensure that the global minimum is updated correctly.

**File:** `POSIX/main.cpp`

### SIMD

The SIMD implementation uses intrinsic functions to perform parallel computations on the array. It leverages the `__m128` type and associated functions to load, compare, and find the minimum values in parallel.

**File:** `SIMD/main.cpp`

## Results

The performance of each implementation is measured by the execution time and the speedup achieved compared to the serial version. The results are printed to the console, showing the serial and parallel run times, speedup, and the minimum values found by each method.

## Usage

To compile and run the programs, navigate to the respective directory and use the following commands:

### OpenMP

```sh
g++ -fopenmp -o OpenMPMinFinder main.cpp
./OpenMPMinFinder
```

### POSIX 

```sh
g++ -pthread -o POSIXMinFinder main.cpp
./POSIXMinFinder
```

### SIMD 

```sh
g++ -msse -o SIMDMinFinder main.cpp -march=native
./SIMDMinFinder
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
