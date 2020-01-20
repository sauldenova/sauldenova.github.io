---
layout: page
title: School Projects
permalink: /school_projects
---

## Capstone project

Instead of doing a thesis, our university requires us to make a capstone project. The project is assigned to a team from a raffle. The project we were assigned was to create a platform that automatically evaluated students for Introduction to programming in Python. The project had the following requirements:

1. Ranked students for different skill levels 1-9. And made them repeat questions if they were wrong.
2. The problems were defined by the following:
    1. Inputs and outputs to determine if a solution is right.
    2. Forbid certain operators for cetrain problems. Ex. banned `for` in exercises that required `while`.
    3. Skill level of the problem.
3. Allow for new problems to be uploaded by the professor.
4. The page can be accessed by students while inside the university.

The project and all code was kept by the Professor and is not available on github.

## Compilers project

The compilers project was a project to create a full compiler for the C-- language. I decided to use an [LLVM backend](https://llvm.org/).

The language is a subset of C with:

1. Function declarations and function calling.
2. Variables and scoping.
3. Types: Boolean, integer, void, double, string.
4. Readline, Print.

An example program that calculates factorial:

```cpp
int fact(int n) {
    int result;
    if (n == 1) {
        result = 1;
    } else {
        result = n * fact(n - 1);
    }

    return result;
}

int main() {
    int n;
    n = readInt();
    print(fact(n), "\n");

    return 0;
}
```

The full project [is in github](https://github.com/sauldenova/cmm-compiler-project)

## Terrain elevation generation

This project was made for the Multicore programming topic. I was inspired by Dwarf Fortress terrain generation and wanted to investigate how it is made. Unfortunately, because of constraints from the class (I was required to use an algorithm that was easily parallelizable) I had to use the [Diamond-Square algorithm](https://en.wikipedia.org/wiki/Diamond-square_algorithm).

| Generated terrain 1                                                                  | Generated terrain 2
| :----------------------------------------------------------------------------------: | :--------------:
| <img src="/assets/images/map.png" altText="Example map 1" width="300" height="300"/> | <img src="/assets/images/map_assembly.png" altText="Example map 2" width="300" height="300"/>

The project made us implement an algorithm with 3 different multi thread frameworks that we had learnt in class. I used:

1. [Java streams](https://docs.oracle.com/javase/tutorial/collections/streams/parallelism.html)
2. [OpenMP](https://en.wikipedia.org/wiki/OpenMP) with C++.
3. [SIMD](https://en.wikipedia.org/wiki/SIMD) instructions for x86 assembly.

The full project [is again in github](https://github.com/sauldenova/parallel-terrain-generation)
