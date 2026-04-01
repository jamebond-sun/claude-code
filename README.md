# Claude Code

&gt; **⚠️ 注意：本源码仅用于教育和研究目的。请尊重知识产权和相关法律法规。**

这是从 Claude Code CLI 工具中提取的完整源代码。Claude Code 是 Anthropic 开发的 AI 编程助手，通过命令行界面与 Claude 模型交互，辅助软件开发工作。

## 功能特性

### 🔧 强大的工具系统

Claude Code 提供了丰富的工具集：

| 类别 | 工具 |
|------|------|
| **文件操作** | `FileReadTool`, `FileWriteTool`, `FileEditTool`, `GlobTool`, `GrepTool` |
| **系统交互** | `BashTool`, `PowerShellTool`, `AskUserQuestionTool` |
| **任务管理** | `TaskCreateTool`, `TaskUpdateTool`, `TaskListTool`, `TaskGetTool`, `TaskStopTool` |
| **Agent 协作** | `AgentTool`, `SendMessageTool` |
| **网络访问** | `WebSearchTool`, `WebFetchTool` |
| **计划模式** | `EnterPlanModeTool`, `ExitPlanModeTool` |
| **Git 工作树** | `EnterWorktreeTool`, `ExitWorktreeTool` |
| **MCP** | `MCPTool`, `ListMcpResourcesTool`, `ReadMcpResourceTool`, `McpAuthTool` |
| **其他** | `SkillTool`, `ConfigTool`, `NotebookEditTool`, `ScheduleCronTool`, `SleepTool`, `LSPTool` |

### 🌐 MCP (Model Context Protocol)

完整的 MCP 协议实现，支持：
- 工具注册与发现
- 资源管理
- 服务端/客户端通信
- 认证机制

### 🔐 权限与安全

- 多级权限模式 (PermissionMode)
- 工具验证配置
- 隐私级别控制
- MDM 管理支持

### 📊 分析与计费

- 使用量追踪
- 成本统计 (cost-tracker)
- Analytics 集成

## 项目结构

```
src/
├── QueryEngine.ts              # 核心查询引擎
├── Tool.ts                     # 工具基类定义
├── tools.ts                    # 工具注册中心
├── context.ts                  # 上下文管理
├── history.ts                  # 对话历史
├── commands.ts                 # 内置命令
├── tasks.ts                    # 任务系统
├── cost-tracker.ts             # 费用追踪
├── setup.ts                    # 初始化设置
├── tools/                      # 所有工具实现
│   ├── AgentTool/
│   ├── BashTool/
│   ├── FileReadTool/
│   ├── FileWriteTool/
│   ├── FileEditTool/
│   ├── GlobTool/
│   ├── GrepTool/
│   ├── WebSearchTool/
│   ├── WebFetchTool/
│   ├── TaskCreateTool/
│   ├── TaskUpdateTool/
│   ├── EnterPlanModeTool/
│   ├── ExitPlanModeTool/
│   ├── MCPTool/
│   ├── SkillTool/
│   └── ... (40+ 工具)
├── services/
│   ├── mcp/                    # MCP 服务实现
│   ├── analytics/              # 分析服务
│   ├── oauth/                  # OAuth 认证
│   └── remoteManagedSettings/  # 远程设置同步
├── utils/
│   ├── git/                    # Git 工具集
│   ├── settings/               # 设置管理
│   ├── permissions/            # 权限系统
│   ├── model/                  # 模型配置
│   ├── shell/                  # Shell 提供者
│   ├── env.ts                  # 环境变量
│   ├── platform.ts             # 平台检测
│   ├── path.ts                 # 路径工具
│   ├── file.ts                 # 文件工具
│   └── ...
├── entrypoints/
│   ├── init.ts                 # 初始化入口
│   ├── mcp.ts                  # MCP 入口
│   ├── agentSdkTypes.ts        # Agent SDK 类型
│   └── sandboxTypes.ts         # 沙箱类型
├── ink/                        # Ink CLI UI 组件
├── schemas/                    # Zod 验证模式
├── types/                      # TypeScript 类型定义
├── constants/                  # 常量定义
├── bootstrap/                  # 启动引导
└── vendor/                     # 第三方代码
```

## 核心架构

### Query Engine

`QueryEngine.ts` 是核心编排器，负责：
- 管理对话上下文
- 工具调用执行
- 响应处理
- 状态管理

### Tool System

每个工具继承自基类 `Tool`，定义在 `src/Tool.ts`：
- 工具描述与参数定义
- 权限级别配置
- 执行逻辑实现

### Settings System

完整的设置管理系统：
- 全局/用户/项目三级配置
- JSON Schema 验证
- 远程设置同步
- MDM 支持

## 技术栈

| 技术 | 用途 |
|------|------|
| **TypeScript** | 主要开发语言 |
| **Node.js** | 运行时环境 |
| **Ink** | React for CLI，构建交互式终端 UI |
| **Zod** | 数据验证 Schema |
| **Lodash** | 工具函数库 |
| **node-fetch** | HTTP 请求 |

## 免责声明

本源码仅供技术研究和学习交流使用。任何个人或组织在使用本源码时，应遵守相关法律法规，尊重知识产权，不得将其用于任何商业用途或非法目的。

## 相关链接

- [Anthropic 官方网站](https://www.anthropic.com)
- [Claude Code 文档](https://claude.ai/code)
- [Model Context Protocol](https://modelcontextprotocol.io/)

---

**本仓库仅用于研究目的**

