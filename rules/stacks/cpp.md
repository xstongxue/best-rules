---
description: "C++ 项目编码规范"
globs: ["src/**/*.cpp", "src/**/*.h"]
alwaysApply: true
---

# 项目背景

本项目使用 **C++** 开发高性能的系统级应用程序，目标是提供高效的数据处理和算法实现。

# 编码标准

- 所有代码必须符合 **Google C++ 风格指南**（[Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)）。
- 使用 **4 空格** 进行缩进，禁止使用制表符（Tab）。
- 非成员变量命名使用 **camelCase**，成员变量命名使用**m_camelCase**，常量命名使用 **UPPER_SNAKE_CASE**。
- 函数和方法名使用 **snake_case** 风格。
- 使用 **const** 修饰不变的变量，避免在函数参数中传递非 const 引用。

# 库和框架约束

- 必须使用 **C++11** 标准及以上，不允许使用过时的 C++98/C++03 特性。
- 使用 **STL** 作为标准库，尽量避免依赖第三方库。
- 必须使用 **smart pointers**（如 `std::unique_ptr` 和 `std::shared_ptr`）来管理动态内存，避免使用裸指针。

# 文件结构

- 头文件放在 `src/include` 目录下，源代码文件放在 `src/` 目录下。
- 测试代码应放在 `tests/` 目录下，使用 **Google Test** 框架进行单元测试。

# 文档规范

- 每个函数和类必须有 **Doxygen** 格式的注释，说明其功能、参数和返回值。
- 所有公共 API 方法必须使用 **Doxygen** 注释，包含参数类型和返回类型。

# 安全规范

- 不得使用裸指针管理资源。
- 避免使用不安全的 `sprintf` 和 `gets` 等函数，推荐使用 **C++11** 的 `std::string` 或 `std::vector` 来替代。