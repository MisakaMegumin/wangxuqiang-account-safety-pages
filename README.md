# 个人简介站

## 文件

- `index.html`：仓库根目录静态站点，内联 CSS、无 JS、无 CDN、无外部图片；已清理本地页面编辑器产生的节点标识与辅助样式，直接双击或托管即可运行。
- `.nojekyll`：避免 GitHub Pages 使用 Jekyll 预处理。
- `.github/workflows/deploy-pages.yml`：可选 GitHub Actions 静态发布工作流。
- `astro-src/content/resume.md`：YAML frontmatter 内容单一事实源。
- `astro-src/src/pages/index.astro`：原在线简历布局与样式源代码，仅移除卡通头像并修正文案。

## 发布到 GitHub Pages

**分支发布（无需构建）**：将本目录的**内容**放在 GitHub 仓库根目录，推送到 `main`，在仓库 `Settings → Pages → Build and deployment → Source` 选择 `Deploy from a branch`，分支选 `main`、目录选 `/ (root)` 并保存。不要将整个文件夹作为仓库根目录下的子目录，否则根目录找不到 `index.html`。

**Actions 发布（可选）**：同样将本目录内容放在仓库根目录，在 Pages 的 Source 改选 `GitHub Actions`；包内工作流会在推送 `main` 后上传静态文件并发布。两种来源只选一种。

不论仓库是 `<username>.github.io` 还是普通项目仓库，页面都不引用站点根路径的资源，适用于 GitHub Pages 子路径。

GitHub 官方操作说明：<https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>。

## 更新内容

优先编辑 `astro-src/content/resume.md` 的 YAML frontmatter，再进入 `astro-src/` 安装依赖并执行 `npm run build`，最后将 `dist/index.html` 覆盖仓库根目录的 `index.html`。只改根目录 HTML 也能立即生效，但下次重新构建会覆盖这类改动。
