# ericzzy.fun

独立静态网站，部署于 GitHub Pages，自定义域名为 `www.ericzzy.fun`。

- `index.html`：网站首页，仅提供知识图谱入口。
- `knowledge-graph/`：中小学及高中全学科知识图谱、自适应诊断、题库和孩子档案。

知识图谱镜像自 [xiaoyang111222/cn-math-taxonomy](https://github.com/xiaoyang111222/cn-math-taxonomy)，采用 CC BY-NC 4.0，仅限非商业使用。原项目许可证、署名和第三方组件许可证均保留在对应目录中。

## 本地预览

```bash
python3 -m http.server 8000
```

访问 `http://localhost:8000/` 或 `http://localhost:8000/knowledge-graph/`。

## 发布

推送到 `main` 后由 GitHub Pages 自动发布。DNS 需将 `www.ericzzy.fun` 的 CNAME 记录指向 `vainturerous-Guan.github.io`。
