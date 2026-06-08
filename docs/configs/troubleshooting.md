# 配置常见错误排查

这份表用于 DeepSeek、Qwen、Roo Code、Qwen Code CLI 的第一轮配置排查。

## API key 错误

现象：

- 返回 `401`、`unauthorized`、`invalid api key`。

处理：

- 确认 key 没有多余空格。
- 确认 key 对应的服务商和 base URL 匹配。
- 确认没有把 DeepSeek key 填到 Qwen provider。
- 确认 key 没被写进仓库。

## Base URL 错误

现象：

- 返回 `404`、`not found`、`provider not supported`。

处理：

- DeepSeek OpenAI-compatible base URL 使用官方当前文档。
- Qwen / 阿里云不同渠道可能有不同 base URL。
- 不要混用 `/v1`、`/chat/completions` 和 provider 自动拼接路径。

## 模型名错误

现象：

- 返回 `model not found`、`invalid model`。

处理：

- 到模型供应商控制台查看当前可用模型。
- 不要使用过期教程里的模型名。
- 先用默认推荐模型跑通，再换高阶模型。

## Roo Code 无法调用

现象：

- 扩展没有响应。
- 请求一直失败。
- 输出空白。

处理：

- 检查 provider 是否选对。
- 检查 base URL、key、model 三项。
- 先用只读小任务测试。
- 降低上下文长度和输出长度。
- 查看 VS Code 扩展日志。

## Qwen Code CLI 不可用

现象：

- `qwen` 命令找不到。
- npm 安装失败。
- Windows 终端无法识别命令。

处理：

- 确认 Node.js 和 npm 已安装。
- 检查 npm 全局 bin 路径是否在 PATH。
- 重新打开终端。
- 用 `npm list -g --depth=0` 确认包是否安装。

## AI 修改范围过大

现象：

- 一次改太多文件。
- 引入无关依赖。
- 删除原有逻辑。

处理：

- 在项目规则中写明“只做最小改动”。
- 先要求 AI 输出计划。
- 每次只允许修改 1-3 个相关文件。
- 修改后必须人工看 `git diff`。

## 敏感文件风险

现象：

- AI 想读取 `.env`。
- AI 输出 token 或连接串。
- AI 想修改部署配置。

处理：

- 立即停止任务。
- 把敏感文件加入禁止列表。
- 轮换已经暴露的 key。
- 重新设置项目规则。

## 最小排查顺序

1. 只读任务能不能跑。
2. provider 是否选对。
3. base URL 是否正确。
4. key 是否有效。
5. model name 是否当前可用。
6. 是否触发上下文或速率限制。
7. 是否被项目规则或安全策略阻止。
