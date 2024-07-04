[English README](./README_EN.md)

# pyot

这是一个 Demo，用于展示如何在 Python 中调用 Rust 代码。实质上是使用 Rust 编写模块，然后编译成 Python 可调用的库文件。为了更好地编辑器自动补全合代码检查，建议为每个模块编写 `*.pyi`。



## 前提

请确保已经：
    - 使用 `rustup` 完成 Rust 工具链的安装
    - 安装了 `rye` 用来管理 Python 工具链

## 开发流程

1. 在 `src/lib.rs` 中编写 Rust 代码
2. `rye sync` 进行编译
3. 在 `python/pyot/__init__.py` 中导入对应的 Rust 函数 （<pyot> 换成实际的项目名称）
4. 在 `python/pyot/__init__.pyi` 中编写类型提示文件（写出函数签名即可）
5. 在其它包中导入并调用 `pyot`。

这里的 Rust 代码合 `pyot` 都是库包，所以需要通过测试或者外部包进行调用。为了便于测试，本项目包装了一个 `example/main.py`，在里面编写代码即可，然后运行 `rye run dev` （等效于 `.venv/bin/python example.py`）。