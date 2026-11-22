# 使用指南

1. 修改 `docs/` 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 `main` 分支（在 GitHub 网页上直接 Commit changes 同样会触发部署）。
4. 在 Actions 页面查看 `build` 与 `deploy` 两个任务的状态。
5. 打开网站检查内容是否更新，必要时强制刷新排除缓存。

## 常用命令

- `python -m mkdocs serve`：本地预览，默认地址 `http://127.0.0.1:8000/`。
- `python -m mkdocs build --strict`：构建网站，并把任何警告都当作错误。

## 实践提示

这次踩过的两个坑值得记下来：

- 四个页面必须平铺在 `docs/` 下，写成 `docs/docs/about.md` 会让 MkDocs 找不到页面，也会让页面间链接解析到错误的目标。
- `--strict` 下只要有一条失效链接就会让整个构建失败，所以同目录页面之间直接写文件名，例如 `[首页](index.md)`，不要带 `docs/` 前缀，也不要链接到不存在的文件。

> 另外，`docs/**` 在工作流的 `paths` 白名单里，所以只修改 `report/README.md` 不会触发新的构建，这是预期行为，不需要去改工作流。

返回[首页](index.md)，或查看 [API 参考](api.md)。
