# DeepSeek + Roo Code 配置样例

用途：让 Roo Code 通过 DeepSeek API 处理代码阅读、重构、测试生成和文档整理任务。

## 适用场景

- 需要大陆用户更容易访问的模型 API。
- 想用 OpenAI-compatible 格式接入 Roo Code。
- 先做 MVP 验证，不想搭复杂模型网关。

## 前置条件

- 已安装 VS Code。
- 已安装 Roo Code 扩展。
- 已有 DeepSeek API key。
- 项目仓库已经打开在 VS Code 中。

## 推荐配置

在 Roo Code 的 provider 设置中选择 OpenAI-compatible 或同类自定义 API provider。

| 项目 | 示例值 |
| --- | --- |
| Base URL | `https://api.deepseek.com` |
| API Key | `DEEPSEEK_API_KEY` |
| Model | 以 DeepSeek 控制台当前可用模型为准 |
| Temperature | `0.2` 到 `0.4` |
| Max Tokens | 按任务复杂度设置 |

注意：DeepSeek 官方文档显示 API 采用 OpenAI-compatible 方式，base URL 为 `https://api.deepseek.com`。模型名称可能调整，正式交付前以官方模型列表为准。

## 项目规则建议

把下面规则加入 Roo Code 项目规则：

```md
先阅读相关文件，再提出修改计划。
只做当前任务需要的最小改动。
不要自动提交 Git。
不要读取或输出 `.env`、token、cookie、私钥。
修改后给出测试命令和验证结果。
```

## 第一次测试任务

让 Roo Code 执行一个只读任务：

```text
请阅读这个项目的 README 和主要源码入口，输出：
1. 项目用途
2. 技术栈
3. 目录结构
4. 你建议优先补充的测试

只读分析，不要修改文件。
```

如果这个任务能稳定完成，再尝试小范围修改。

## 安全注意事项

- 不要把 API key 写进仓库。
- 不要让 AI 修改生产部署配置。
- 不要让 AI 自动运行未知脚本。
- 先让 AI 解释计划，再允许它修改文件。
- 每次修改后人工查看 `git diff`。

## 验收标准

- Roo Code 能正常调用 DeepSeek。
- AI 能读项目并输出结构化分析。
- 没有修改任何敏感文件。
- 用户知道下一步如何尝试小任务。

## 参考链接

- DeepSeek API Docs: https://api-docs.deepseek.com/
- Roo Code Providers: https://roocodeinc.github.io/Roo-Code/providers/
