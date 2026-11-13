# AGENTS.md · 项目约定

## 项目简介

纯静态独立网站（HTML + CSS + 原生 JS，无框架、无构建工具），部署于 GitHub Pages，自定义域名 `www.ericzzy.fun`。定位为中小学生的学习、自测与成就平台。与 `ericzzy_com` 日常记录项目分仓库、分域名管理，不要向本站加入日常记录或股票功能。

## 页面结构

- `index.html`：门户首页。上半区域三个频道入口（打怪版/打扮版/中学生），下半区域「你可以做什么」三步说明 + 「浏览全部知识」（指向 `/knowledge-graph/explore/`）。
- `about/`：网站介绍页，全站顶部菜单「网站介绍」指向它。通过 `<base href="/knowledge-graph/">` 复用知识图谱的静态资源和 `home.js`。
- `knowledge-graph/`：完整镜像 `xiaoyang111222/cn-math-taxonomy`，含全学科知识图谱、自适应诊断、题库和孩子档案，无需构建。其 `index.html` 是重定向页（hash 转发到 `explore/`，其余跳 `/about/`），旧分享链接不能破坏。
- `game-data/`：频道静态配置（奖励映射 `rewards.json`、题库覆盖 `coverage.json`），说明见其 README。

## 频道约定

- 频道用 `explore/?channel=monster|dressup|teen` 实现：`monster`/`dressup` 锁定小学学段（1–6 年级，语数英科道五科），`teen` 为全量。频道页内必须保留通往全量图谱的入口（顶部「知识图谱」菜单与频道条「查看全部知识」）。
- 打怪版奖励：数学→武器，语文→衣服，英语→鞋子，其他学科→武功秘籍；打扮版：数学→项链头冠，语文→衣服，英语→鞋子，其他学科→配饰；中学生·成就版只有本机成就称号，无打怪打扮内容，不分男女。第一期奖励仅数值/图鉴展示，不改变答题规则；跨用户排名等登录机制上线后再做。
- 进度与孩子档案一样存浏览器 localStorage，不上传。

## 知识图谱约定

- 遵循 CC BY-NC 4.0，仅限非商业使用；署名、来源与 `LICENSE` 保留在仓库（`LICENSE` 文件、`README.md`），页面上不展示署名页脚（全站页脚行已按站主要求移除）。`assets/vendor/` 的第三方组件继续使用各自 MIT 许可证。
- 本站适配包括：左下角返回 `https://www.ericzzy.fun/` 的悬浮首页图标、按当前域名生成分享链接、顶部菜单（网站介绍/知识图谱/诊断/档案/频道下拉，不放「关于」）。
- 原项目数据与代码更新时同步整个 `knowledge-graph/` 目录，但需保留上述本站适配（含 `explore/app.js` 的频道模式）。
- 修改页面壳、脚本、样式或缓存列表后，递增 `knowledge-graph/sw.js` 中的缓存版本。

## 部署

部署即 push 到 `main`，GitHub Pages 从仓库根目录发布。DNS 中 `www` 的 CNAME 指向 `vainturerous-Guan.github.io`。
