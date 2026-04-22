---
description: "Go 项目编码规范"
globs: ["src/**/*.go"]
alwaysApply: true
---

# 项目背景
本项目使用 **Go** 开发高效的后端服务，目标是构建高并发、低延迟的服务架构。

# 编码标准
- 所有代码必须符合 **Go 官方编码规范**（[Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)）。
- 使用 **gofmt** 格式化工具，强制所有代码符合 Go 的格式要求。
- 函数和变量命名使用 **camelCase**，但包名必须使用 **lowercase** 风格。
- 避免过多的注释，代码自解释，确保简洁和易读。

# 库和框架约束
- 必须使用 **Gin** 或 **Echo** 作为 Web 框架，禁止使用其他框架。
- 必须使用 **Gorm** 或 **sqlx** 作为数据库库，禁止直接操作 SQL。
- 网络请求必须使用 **http.Client**，不得使用第三方网络库。
- 使用 **golangci-lint** 进行静态代码分析。

# 文件结构
- 所有源代码放在 `src/` 目录下，测试代码放在 `tests/` 目录下。
- 配置文件存放在 `config/` 目录，模型和数据结构定义放在 `models/` 目录。

# 文档规范
- 所有函数和接口必须写详细的文档，使用 **GoDoc** 格式。
- API 接口必须有明确的输入输出说明，并且提供示例请求和响应。

# 安全规范
- 避免在代码中硬编码任何 **API 密钥** 或 **密码**，应该通过环境变量或配置文件传入。
- 使用 **context.Context** 来处理请求的超时和取消，避免阻塞操作。