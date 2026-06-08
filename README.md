# 国内可用 AI 编程工作流套件

这是一个面向中国大陆开发者和小团队的最小可爱 MVP。

目标不是提供 OpenAI/Codex 访问通道，而是用国内可用模型和开源工具，搭建接近 Codex 使用体验的 AI 编程工作流。

## MVP 包含

- 静态进度站点：`index.html`
- Roo Code 项目规则模板：`templates/roo-code-rules.md`
- AI 编程安全检查表：`templates/security-checklist.md`
- 早期用户访谈表：`templates/pilot-intake.md`
- MVP 作战手册：`docs/playbook.md`
- DeepSeek + Roo Code 配置样例：`docs/configs/deepseek-roo-code.md`
- Qwen + Roo Code 配置样例：`docs/configs/qwen-roo-code.md`
- Qwen Code CLI 安装与试运行：`docs/configs/qwen-code-cli.md`
- 配置常见错误排查：`docs/configs/troubleshooting.md`

## 推荐技术组合

- Agent：Roo Code、Qwen Code
- 模型：DeepSeek、Qwen、OpenAI-compatible provider、本地模型
- 代码平台：GitHub、Gitee、极狐 GitLab
- 私有知识库：FastGPT 或同类 RAG 工具
- 安全：人工 review、敏感文件黑名单、禁止自动部署

## 本地查看

直接打开 `index.html` 即可查看站点。

## 迭代方向

1. 补齐 DeepSeek / Qwen 配置截图。
2. 增加 10 个真实开发案例。
3. 增加小班课讲义。
4. 增加团队落地 checklist。
