# Qwen Code CLI 安装与试运行

用途：用 Qwen Code 在终端里完成仓库级阅读、脚本化分析、文档整理和小范围代码任务。

## 适用场景

- 用户喜欢终端工作流。
- 需要在 Git 仓库里执行连续任务。
- 想把 AI 编程流程接入 shell、CI 或本地脚本。

## 安装

官方文档提供 npm 安装方式：

```bash
npm install -g @qwen-code/qwen-code@latest
```

安装后确认命令可用：

```bash
qwen --version
```

如果 Windows 上全局 npm 路径不可用，需要检查 Node.js 和 npm 全局 bin 路径。

## 首次配置

根据你选择的 Qwen / 阿里云 / OpenAI-compatible provider 设置认证信息。

不要把 key 写进仓库。推荐通过环境变量或 CLI 官方支持的登录方式配置。

示例占位：

```bash
set QWEN_API_KEY=你的_key
```

PowerShell 示例：

```powershell
$env:QWEN_API_KEY="你的_key"
```

## 第一次只读任务

进入项目目录后执行：

```bash
qwen -p "请只读分析这个仓库：总结项目用途、技术栈、目录结构和最适合先补测试的模块。不要修改文件。"
```

## 团队使用建议

- 先让 Qwen Code 做只读分析。
- 再让它输出计划。
- 只允许它改小范围文件。
- 修改后必须人工查看 diff。
- 重要改动走 PR/MR。

## 安全注意事项

- 不要在命令行历史里留下真实 key。
- 不要让 AI 自动执行未知安装脚本。
- 不要让 AI 读取 `.env`、私钥、cookie、token。
- 不要让 AI 自动部署生产环境。

## 验收标准

- `qwen --version` 能运行。
- 只读仓库分析能完成。
- 没有产生非预期文件修改。
- 用户知道如何进入下一步小任务。

## 参考链接

- Qwen Code: https://github.com/QwenLM/qwen-code
