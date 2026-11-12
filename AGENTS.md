# AGENTS.md · 项目约定

## 项目简介

纯静态独立网站（HTML + CSS + 原生 JS，无框架、无构建工具），部署于 GitHub Pages，自定义域名 `www.ericzzy.fun`。与 `ericzzy_com` 日常记录项目分仓库、分域名管理，不要向本站加入日常记录或股票功能。

## 页面结构

- `index.html`：空白简洁首页，仅保留【知识图谱】入口，链接到 `/knowledge-graph/`。
- `knowledge-graph/`：完整镜像 `xiaoyang111222/cn-math-taxonomy`，含全学科知识图谱、自适应诊断、题库和孩子档案，无需构建。

## 知识图谱约定

- 遵循 CC BY-NC 4.0，仅限非商业使用，必须保留原项目署名、来源和 `LICENSE`；`assets/vendor/` 的第三方组件继续使用各自 MIT 许可证。
- 本站适配包括：左下角返回 `https://www.ericzzy.fun/` 的悬浮首页图标、页脚来源说明、按当前域名生成分享链接。
- 原项目数据与代码更新时同步整个 `knowledge-graph/` 目录，但需保留上述本站适配。
- 修改页面壳、脚本、样式或缓存列表后，递增 `knowledge-graph/sw.js` 中的缓存版本。

## 部署

部署即 push 到 `main`，GitHub Pages 从仓库根目录发布。DNS 中 `www` 的 CNAME 指向 `vainturerous-Guan.github.io`。
