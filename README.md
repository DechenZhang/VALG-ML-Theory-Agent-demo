# VALG Research Demo Site

`site/` 是 VALG-ML-Theory-Agent 的静态展示站点，首页只保留三个入口：skill 介绍、安装与使用、案例。

## 页面结构

- `index.html`：中文 skill 介绍、工作流图片、安装运行摘要和案例入口；
- `install.html`：详细的安装、Codex CLI 和 GetRun 使用说明；
- `cases.html`：按研究主题整理的 9 个 subproblem 卡片；
- `case-*.html`：每个 subproblem 的 source question、progress 和 solution 摘要。

每个 solution 详情只保留 `Source PDF` 和 `Result PDF` 两个材料链接。Partial progress 会同时说明 relaxation 和 remaining gap。

## 本地预览

从 demo 根目录启动静态服务器：

```bash
bash scripts/serve-results.sh
```

然后打开 <http://127.0.0.1:8000/>。站点只使用本地 HTML、CSS、图片和案例 PDF，不依赖 npm、CDN 或运行时 API。

## 重新生成

案例摘要来自 `data/results.json`。修改生成器或案例数据后运行：

```bash
python3 scripts/build-site-content.py
```

生成器会更新首页、安装使用专页、案例总览和 9 个 subproblem 详情页。安装使用专页以 GitHub 上游仓库的 `skills/` 为实际安装来源；本 demo 根目录的脚本只用于站点维护和本地验证。
