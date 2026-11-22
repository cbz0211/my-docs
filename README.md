# my-docs

本项目是「实践项目 2：通过 GitHub Actions 自动部署静态文档到 GitHub Pages」的个人作业仓库。四页文档用 Markdown 编写，由 MkDocs Material 构建，推送到 main 后由工作流自动部署到 GitHub Pages。

- 网站地址：https://cbz0211.github.io/my-docs/
- 源码仓库：https://github.com/cbz0211/my-docs
- [个人实验报告](report/README.md)

## 本地预览

```bash
python -m venv .venv
source .venv/Scripts/activate          # Windows Git Bash；其他终端见作业说明
python -m pip install -r requirements.txt
python -m mkdocs serve
```

浏览器打开 http://127.0.0.1:8000/ 逐页检查；构建检查用 `python -m mkdocs build --strict`。
