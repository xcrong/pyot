# pyot

This is a demo to show how to call Rust code in Python. Essentially, it involves writing modules in Rust and then compiling them into library files callable from Python. To improve editor auto-completion and code checking, it is recommended to write `*.pyi` files for each module.

## Prerequisites

Please ensure you have:
    - Installed the Rust toolchain using `rustup`
    - Installed `rye` to manage the Python toolchain

## Development Process

1. Write Rust code in `src/lib.rs`
2. Compile using `rye sync`
3. Import the corresponding Rust functions in `python/pyot/__init__.py` (replace <pyot> with the actual project name)
4. Write type hint files in `python/pyot/__init__.pyi` (just write the function signatures)
5. Import and call `pyot` in other packages.

Both the Rust code and `pyot` are library packages, so they need to be called through tests or external packages. To facilitate testing, this project wraps an `example/main.py` where you can write code and then run `rye run dev` (equivalent to `.venv/bin/python example.py`).