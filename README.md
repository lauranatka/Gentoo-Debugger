# Gentoo Multi-Language Debugger

A lightweight **multi-language debugging and diagnostic project** for Gentoo Linux.

The project is designed as a collection of language-specific components for testing compiler functionality, runtime behavior, memory handling, system information, and common programming features.

Currently, this repository includes the **C / GCC component**.

## 🚀 Current Features

The C/GCC debugger performs a collection of automated diagnostic tests:

* 🧮 Integer arithmetic
* 🔢 Floating-point calculations
* 📦 Array operations
* 🔤 String handling
* 👉 Pointer dereferencing
* 🧠 Dynamic memory allocation
* 🏗️ C structures
* ⚠️ `errno` error handling
* 🔁 `for` loops
* 🖥️ System information
* 📊 Test result summary

The program keeps track of the total number of tests, successful tests, and failed tests.

## 🛠️ Requirements

* Gentoo Linux or another Unix-like system
* GCC
* C17 support
* Standard C library
* `libm` / math library
* POSIX-compatible system APIs

The program uses headers including `unistd.h` and `sys/utsname.h` for system-level information.

## 📥 Compilation

Compile the C component with GCC:

```bash
gcc -std=c17 -Wall -Wextra -pedantic -O2 \
    -o gentoo_debugger gentoo_debugger.c -lm
```

The source itself specifies C17, warning flags, optimization, and linking against the math library.

## ▶️ Running

After compilation:

```bash
./gentoo_debugger
```

The debugger starts the C/GCC test suite automatically.

## 📊 Example Output

```text
========================================
       Gentoo C Debugger v1.0
========================================

Starte C/GCC Debug-Tests...

[OK]   Mathematik               25 + 17 = 42
       Difference: 8
       Product:    425

[OK]   Floating Point           Berechnung erfolgreich
       PI^2 = 9.869604

[OK]   Arrays                   Array-Test erfolgreich
       Elemente: 5
       Summe:     150

[OK]   Strings                  String-Verarbeitung erfolgreich
       Text: Gentoo C Debugger

[OK]   Pointer                  Pointer-Dereferenzierung erfolgreich

[OK]   Memory                   malloc/free erfolgreich

[OK]   Struct                   Struktur-Test erfolgreich

[OK]   Error Handling           errno-Test erfolgreich

[OK]   Loops                    for-Schleife erfolgreich

========================================
             Ergebnisse
========================================
Tests          : 9
Erfolgreich    : 9
Fehlgeschlagen : 0
========================================

[SUCCESS] Alle C-Tests erfolgreich!
```

## 🔍 Test Modules

### Mathematics

Tests basic integer arithmetic using addition, subtraction, and multiplication.

```c
int sum = a + b;
int difference = a - b;
int product = a * b;
```

The expected arithmetic result is `25 + 17 = 42`.

### Floating Point

Tests floating-point calculations using `double` and `fabs()`.

```c
const double value = 3.141592653589793;
const double squared = value * value;
```

The result is compared against an expected value using a tolerance.

### Arrays

Creates an integer array, calculates its size with `sizeof`, iterates through its elements, and verifies the resulting sum.

### Strings

Uses `snprintf()` to construct a string and `strstr()` to verify that it contains `"Gentoo"`.

### Pointers

Tests pointer creation, NULL checking, and pointer dereferencing.

```c
int value = 42;
int *pointer = &value;
```

The test verifies that the pointer is valid and points to the expected value.

### Dynamic Memory

Tests dynamic allocation with `malloc()` and cleanup with `free()`.

```c
int *numbers = malloc(count * sizeof(*numbers));
```

The allocated memory is populated, validated, and released.

### Structures

Tests a custom `Computer` structure containing:

```text
name
cores
debug
```

The structure is initialized and its fields are validated.

### Error Handling

Tests the `errno` mechanism using `ENOENT`.

```c
errno = ENOENT;
```

### Loops

Tests a simple `for` loop and verifies that the counter reaches the expected value.

## 🖥️ System Information

After running the tests, the program displays information obtained from the host system.

The output includes:

* Operating system
* Kernel version
* Architecture
* Hostname
* Online CPU core count
* C standard
* Compiler

The system information is gathered using `uname()` and `sysconf()`.

## 📈 Test Results

The debugger maintains three counters:

```text
Tests
Successful
Failed
```

If no tests fail, the program reports:

```text
[SUCCESS] Alle C-Tests erfolgreich!
```

Otherwise it displays a warning indicating that some tests failed.

## 🏗️ Project Structure

The intended project structure is:

```text
gentoo-multi-language-debugger/
│
├── C/
│   └── gentoo_debugger.c
│
├── Rust/
│   └── ...
│
├── Python/
│   └── ...
│
├── Ruby/
│   └── ...
│
├── Shell/
│   └── ...
│
├── README.md
├── LICENSE
└── Makefile
```

Additional language components can be added independently as the project develops.

## 🧪 Development

The current C component is version:

```text
1.0
```

The version is defined directly in the source:

```c
#define VERSION "1.0"
```

Recommended development compilation:

```bash
gcc -std=c17 -Wall -Wextra -pedantic -O2 \
    -o gentoo_debugger gentoo_debugger.c -lm
```

For debugging the debugger itself, a development build can also be compiled with:

```bash
gcc -std=c17 -Wall -Wextra -pedantic -g \
    -o gentoo_debugger_debug gentoo_debugger.c -lm
```

Then use GDB:

```bash
gdb ./gentoo_debugger_debug
```

## 🤝 Contributing

Contributions are welcome.

Possible areas for contribution:

* Additional C tests
* Better diagnostic output
* More system checks
* Unit-test integration
* Makefile/CMake support
* Additional language components
* Gentoo-specific diagnostics
* Automated CI testing

### Pull Requests

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Compile with strict warnings
5. Run the debugger
6. Commit your changes
7. Open a Pull Request

Example:

```bash
git checkout -b feature/new-test
git add .
git commit -m "Add new diagnostic test"
git push origin feature/new-test
```

## ⚠️ Disclaimer

Gentoo Multi-Language Debugger is intended for **software development, debugging, diagnostics, and educational purposes**.

The current C component performs local tests and gathers basic system information; it does not claim to perform full application debugging or automated Gentoo package repair.

## 📜 License

This project is released under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.

---

## ⭐ Gentoo Multi-Language Debugger

**Test your code. Inspect your system. Understand your environment.**

**Current component:** C / GCC
**Version:** 1.0
