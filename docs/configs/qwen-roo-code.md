# Qwen + Roo Code 配置样例

用途：让 Roo Code 接入 Qwen 或兼容 Qwen 的 OpenAI-compatible API，用于代码生成、解释、文档整理和测试补全。

## 适用场景

- 团队偏好阿里云 / 通义千问生态。
- 希望在国内云服务和开源工具之间保持较好兼容性。
- 需要为企业试点预留国产模型方案。

## 前置条件

- 已安装 VS Code。
- 已安装 Roo Code 扩展。
- 已有 Qwen 相关 API key 或模型服务接入方式。
- 已确认当前 provider 的 base URL、model name 和计费方式。

## 推荐配置

在 Roo Code 中选择 OpenAI-compatible 或对应 Qwen provider。

| 项目 | 示例值 |
| --- | --- |
| Base URL | 以 Qwen / 阿里云控制台为准 |
| API Key | `QWEN_API_KEY` |
| Model | 以当前控制台可用模型为准 |
| Temperature | `0.2` 到 `0.4` |
| Max Tokens | 按任务复杂度设置 |

不同 Qwen 渠道的 base URL 和模型名可能不同。文档中不要硬编码真实 key 或账号信息。

## 第一次测试任务

```text
请只读分析当前项目：
1. 找出入口文件
2. 总结主要模块
3. 说明哪些文件最适合先写测试
4. 输出一个 3 步最小改造计划

不要修改文件，不要运行命令。
```

## 适合 Qwen 的任务

- 中文需求理解。
- 中文文档整理。
- 代码解释。
- 测试用例草稿。
- 接口文档初稿。

## 安全注意事项

- 不要把云控制台截图、key、账号信息交给 AI。
- 不要把生产数据库连接串放入上下文。
- 不要开启自动提交或自动部署。
- 企业试点时需要记录模型供应商、数据范围和权限边界。

## 验收标准

- Roo Code 能调用 Qwen 相关服务。
- AI 能完成只读项目分析。
- 输出内容能被开发者理解并继续执行。
- 没有泄露或提交任何敏感配置。

## 参考链接

- Qwen Code: https://github.com/QwenLM/qwen-code
- Roo Code Providers: https://roocodeinc.github.io/Roo-Code/providers/
