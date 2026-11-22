# 关于本项目

## 项目目标

把 Markdown 文档变成一个公开可访问的网站，并做到「推送文档 → 自动构建 → 自动部署 → 网页更新」，不需要手工上传生成好的网页文件。

## 源码、产物、工作流与网站

- `docs/` 是手写的 Markdown 源码，是唯一需要长期维护的内容。
- `site/` 是 `mkdocs build` 生成的静态网站，每次构建都会重新生成并覆盖，因此写进 `.gitignore`，不提交到 `main`。
- `.github/workflows/deploy.yml` 描述何时构建、如何部署；只有推送命中 `docs/**`、`mkdocs.yml`、`requirements.txt` 或工作流文件本身时才运行。
- GitHub Pages 是最终托管网站的地方，由 `deploy` 任务把构建产物发布过去。

因为产物由工作流自动生成并作为 artifact 上传，本次方案不需要 `gh-pages` 分支，也不需要手工修改 `site/`。

## 技术组成

| 工具 | 作用 |
| --- | --- |
| Markdown | 编写文档内容 |
| MkDocs Material | 将文档构建成静态网站 |
| GitHub Actions | 自动执行安装、构建和部署 |
| GitHub Pages | 托管并提供网站访问地址 |

> 换句话说，我维护的是源码，网站是这份源码经过构建后的一份快照；每次推送都会重新生成一份新快照。

返回[首页](index.md)，或查看[使用指南](guide.md)。
