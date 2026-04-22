---
description: "Vue 3 项目编码规范"
globs: ["src/**/*.vue"]
alwaysApply: true
---

# 项目背景
本项目使用 **Vue 3** + **TypeScript** + **Vuex**，后端提供 RESTful API。目标是构建一个响应式、高性能的前端应用。

# 编码标准
- 所有组件必须使用 **Vue 3** 的 Composition API，不允许使用 Options API。
- 所有代码必须使用 **TypeScript**，不允许使用 **JavaScript**。
- 变量命名使用 **camelCase**，组件命名使用 **PascalCase**。
- Vue 组件的模板部分和脚本部分之间应该使用空行分隔。

# 库和框架约束
- 使用 **Vue Router** 来进行路由管理。
- 使用 **Vuex** 来进行状态管理，避免直接在组件中存储状态。
- 使用 **Vite** 作为构建工具，不得使用 **webpack**。
- 使用 **TailwindCSS** 进行样式管理，禁止使用内联样式。

# 文件结构
- 组件应放在 `src/components` 目录下，页面组件放在 `src/pages` 下。
- 所有 API 调用应封装在 `src/api` 目录下。
- 所有共享的工具函数和自定义钩子应放在 `src/utils` 下。

# 文档规范
- 组件文件顶部必须有模块注释，说明组件的功能、Props 和事件。
- 所有公共 API 方法必须使用 **JSDoc** 写注释，注明参数和返回值类型。

# 安全规范
- 不得将 **API Key** 和 **敏感信息** 明文写在代码中。
- 配置文件和环境变量应从 `.env` 文件中读取，不应硬编码在代码中。