## 1. 项目概览

- 项目用途：待补充
- 技术栈：待补充
- 主要目录：待补充
- 包管理器：pnpm

## 2. 通用要求

- 遵循现有架构、代码风格及项目约定。
- 全局使用UTF-8编码，包括中文。
- 修改前阅读相关实现及适用规范。
- 完成后说明改动内容、验证结果及尚未解决的问题。

## 3. 规范索引(如不存在实际内容则不引用)

| 规范           | 文档                                             | 阅读时机                                   |
| -------------- | ------------------------------------------------ | ------------------------------------------ |
| 项目与架构     | [architecture.md](docs/standards/architecture.md) | 新增模块、调整结构或依赖时                 |
| 开发工作流     | [workflow.md](docs/standards/workflow.md)         | 初始化环境、执行开发任务时                 |
| 前端规范       | [frontend.md](docs/standards/frontend.md)         | 修改前端库、配置、页面、组件及结构或状态时 |
| UI/UX规范      | [UI\&UX.md](docs/standards/UI&UX.md)              | 修改组件样式以及交互时                     |
| 后端规范       | [backend.md](docs/standards/backend.md)           | 修改服务、业务逻辑或后台任务时             |
| 数据规范       | [data.md](docs/standards/data.md)                 | 修改数据库、迁移或缓存时                   |
| 测试与质量     | [testing.md](docs/standards/testing.md)           | 编写测试及验证变更时                       |
| 安全与隐私     | [security.md](docs/standards/security.md)         | 涉及权限、用户数据或外部输入时             |
| 性能与可观测性 | [performance.md](docs/standards/performance.md)   | 涉及性能、日志、监控时                     |
| Git 与代码评审 | [git.md](docs/standards/git.md)                   | 提交代码或创建 PR 时                       |
| 构建与发布     | [release.md](docs/standards/release.md)           | 修改构建、CI 或部署配置时                  |

## 4. Subagent委派

- 委派前写明目标、范围、验收标准和禁止触碰的边界。
- 按任务范围、依赖复杂度、不确定性、验证难度和失败代价选择满足要求的最低配置：
  - 局部、机械且容易验证：轻量模型 + `low`。
  - 跨文件实现、测试补充或常规调试：标准模型 + `medium`。
  - 架构设计、跨模块链路、疑难问题、高风险变更或跨 agent 协作：高能力模型 + `high`。
- 模型档位映射到当前环境的可用模型，局部项目规则可覆盖。风险升高时先提高推理深度，仍不足再升级模型；已处于最高档时，拆分任务并加强验证。
- 主 agent 核对返回结果的证据、验收标准和工作区状态。结果不满足要求时，先核对任务理解；确因能力或推理不足时升级一档重试一次，否则接管或重新拆分。
