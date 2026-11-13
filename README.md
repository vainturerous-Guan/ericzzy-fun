# ericzzy.fun

独立静态网站，部署于 GitHub Pages，自定义域名为 `www.ericzzy.fun`。定位为中小学生的学习、自测与成就平台。

- `index.html`：网站门户首页。上半区域是三个频道入口（小学生·打怪版、小学生·打扮版、中学生·成就版），下半区域是「你可以做什么」三步说明和「浏览全部知识」入口。
- `about/`：网站介绍页（内容暂沿用知识图谱介绍，后续优化）。所有页面的顶部菜单「网站介绍」指向这里。
- `knowledge-graph/`：中小学及高中全学科知识图谱、自适应诊断、题库和孩子档案。`/knowledge-graph/` 裸地址为重定向页（保留旧分享链接的 hash 转发，其余跳 `/about/`）。
- `game-data/`：三个频道的静态配置数据（奖励映射、成就定义、题库覆盖统计）。

## 频道

通过 `knowledge-graph/explore/?channel=xxx` 进入：

- `monster` 小学生·打怪版（男孩版）、`dressup` 小学生·打扮版（女孩版）：锁定小学学段，只展示语文、数学、英语、科学、道法五个学科和一至六年级；英语一、二年级暂无内容，有空态提示。从频道内点「知识图谱」菜单仍进入全量图谱。
- `teen` 中学生·成就版：全量内容，成就称号后续上线。

打怪/打扮的进度和孩子档案一样保存在浏览器 localStorage，不上传、无账号；静态配置放在 `game-data/`。

知识图谱镜像自 [xiaoyang111222/cn-math-taxonomy](https://github.com/xiaoyang111222/cn-math-taxonomy)，采用 CC BY-NC 4.0，仅限非商业使用。原项目许可证、署名和第三方组件许可证均保留在对应目录中。

## 本地预览

```bash
python3 -m http.server 8000
```

访问 `http://localhost:8000/`、`http://localhost:8000/about/` 或 `http://localhost:8000/knowledge-graph/explore/`。

## 发布

推送到 `main` 后由 GitHub Pages 自动发布。DNS 需将 `www.ericzzy.fun` 的 CNAME 记录指向 `vainturerous-Guan.github.io`。
