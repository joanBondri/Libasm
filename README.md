# Libasm - Introduction to Assembly Language

![GitHub last commit](https://img.shields.io/github/last-commit/joanBondri/Libasm)

## Overview

Libasm is a project created as part of the "Libasm" curriculum at École 42, designed to provide an introduction to Assembly language programming. In this project, we have implemented essential C library functions in Assembly, including `read`, `strcmp`, `strcpy`, `strdup`, `strlen`, and `write`. The goal is to gain a deeper understanding of how these functions work at a low-level, and to become familiar with x86-64 Assembly language.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following requirements:

- A Unix-based operating system (Linux or macOS).
- [NASM](https://www.nasm.us/) (Netwide Assembler) installed on your system.
- [GCC](https://gcc.gnu.org/) (GNU Compiler Collection) for linking and testing your Assembly code.

### Installation

1. Clone this repository to your local machine.

```shell
git clone https://github.com/joanBondri/Libasm.git
cd Libasm
```

2. Build the `libasm.a` library using the provided Makefile.

```shell
make
```

## Usage

To use the `libasm.a` library in your C programs, include the header file `libasm.h` and link against the library.

```c
#include "libasm.h"

int main() {
    // Example code using libasm functions
    int fd = open("example.txt", O_RDONLY);
    char buffer[256];
    ssize_t bytes_read = read(fd, buffer, 255);
    // ...
    close(fd);
    return 0;
}
```

Compile your program with:

```shell
gcc -o my_program my_program.c libasm.a
```

### Testing

This repository also includes a test suite to validate the correctness of your implementation. You can build and run the tests using the following commands:

```shell
make test
```

## Functions

The following functions have been implemented in Assembly language:

- `int ft_strlen(const char *str)`
- `char *ft_strcpy(char *dst, const char *src)`
- `int ft_strcmp(const char *s1, const char *s2)`
- `ssize_t ft_write(int fd, const void *buf, size_t count)`
- `ssize_t ft_read(int fd, void *buf, size_t count)`
- `char *ft_strdup(const char *s1)`
