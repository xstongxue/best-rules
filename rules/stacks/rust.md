---
description: "Rust 项目编码规范"
globs: ["src/**/*.rs"]
alwaysApply: true
---

# 项目背景
本项目使用 **Rust** 开发一个高性能、内存安全的服务应用，目标是提供低延迟和高并发处理能力。

# 编码标准
- 所有代码必须符合 **Rust 官方编码指南**（[Rust Style Guide](https://doc.rust-lang.org/book/)）。
- 变量和函数命名使用 **snake_case**，类型和结构体命名使用 **CamelCase**。
- 所有代码都必须使用 **Rustfmt** 格式化工具，确保一致的代码格式。
- 使用 **Ownership** 和 **Borrowing** 规则，避免使用 `unsafe` 代码块，除非绝对必要。

# 库和框架约束
- 使用 **async-std** 或 **tokio** 来进行异步编程，不得使用 **futures**。
- 必须使用 **serde** 库进行数据序列化和反序列化。
- 使用 **clippy** 进行代码静态分析，确保代码质量。

# 文件结构
- 所有源代码文件放在 `src/` 目录下，测试代码应放在 `tests/` 目录下。
- 配置文件放在 `config/` 目录下。

# 文档规范
- 所有函数和方法必须有 **Rustdoc** 格式的注释。
- 模块和复杂逻辑应写详细的文档，解释设计思路和使用方式。

# 安全规范
- 避免使用 **unsafe**，除非无法避免且经过严格审查。
- 所有网络请求应使用 **reqwest** 或 **hyper** 库，避免直接操作原始套接字。