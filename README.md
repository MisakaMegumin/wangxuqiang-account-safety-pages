# 王续强｜账号安全运营个人简介站

此目录以原在线简历 `https://wangxuqiang.pages.woa.com/` 为版式基准，以本人在 `index.html` 中人工编辑的内容为最终取舍。工作经历、AI 工作流、9 个重点项目、技能与荣誉等板块保留；手工删除和精简的内容已同步到 `astro-src/content/resume.md`，后续重建不会恢复旧文案。原内网站点未修改；不将未证实的事件指挥、跨时区协作或预算职责写成既有经历。英语仅标注 CET-6 水平。

## 文件

- `index.html`：仓库根目录静态站点，内联 CSS、无 JS、无 CDN、无外部图片；已清理本地页面编辑器产生的节点标识与辅助样式，直接双击或托管即可运行。
- `.nojekyll`：避免 GitHub Pages 使用 Jekyll 预处理。
- `.github/workflows/deploy-pages.yml`：可选 GitHub Actions 静态发布工作流。
- `astro-src/content/resume.md`：YAML frontmatter 内容单一事实源。
- `astro-src/src/pages/index.astro`：原在线简历布局与样式源代码，仅移除卡通头像并修正文案。

此前的岗位定向改动：① 重点项目顺序调整为微信账号安全、网易游戏账号安全、支付风控相关项目；② 微信相关描述按「监控发现 → 巡检/熔断与梯度处置 → 审核/客诉 → 质检复盘」闭环重写；③ 在个人信息中增补英语 CET-6；④ 移除手机号、卡通头像以及涉及隐私实现和原始数据留存期限的表述。工作经历仍按原有倒序、全部 9 个项目及技能/荣誉继续保留。

**本次人工定稿同步**：删除财付通工作经历中的一条接口改造说明；将微信知识分享成果改为“获得腾讯年度知识奖”；AI 工作流实践收敛为两条；按人工稿去掉查冻扣项目“内容”一行，保留背景与解决的问题；精简金融一体化、3DS、数币合作、风控数据治理等项目措辞，以及数据分析、AI 应用两张技能卡。页面不保留编辑器空白行、零宽字符或编辑器样式。

## 发布到 GitHub Pages

**分支发布（无需构建）**：将本目录的**内容**放在 GitHub 仓库根目录，推送到 `main`，在仓库 `Settings → Pages → Build and deployment → Source` 选择 `Deploy from a branch`，分支选 `main`、目录选 `/ (root)` 并保存。不要将整个文件夹作为仓库根目录下的子目录，否则根目录找不到 `index.html`。

**Actions 发布（可选）**：同样将本目录内容放在仓库根目录，在 Pages 的 Source 改选 `GitHub Actions`；包内工作流会在推送 `main` 后上传静态文件并发布。两种来源只选一种。

不论仓库是 `<username>.github.io` 还是普通项目仓库，页面都不引用站点根路径的资源，适用于 GitHub Pages 子路径。

GitHub 官方操作说明：<https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>。

## 更新内容

优先编辑 `astro-src/content/resume.md` 的 YAML frontmatter，再进入 `astro-src/` 安装依赖并执行 `npm run build`，最后将 `dist/index.html` 覆盖仓库根目录的 `index.html`。只改根目录 HTML 也能立即生效，但下次重新构建会覆盖这类改动。

## 公开前必审

1. **隐私**：本版已移除原简历手机号、卡通头像和特定账号审核隐私实现/原始数据长期留存描述；邮箱仍会在公开 GitHub Pages 页面被任何人看到。
2. **对外披露**：本版保留原内网站披露的相对改善数据、内部产品名称、项目与奖项；公开发布前请本人确认可对外披露的范围，并能解释统计周期、对照口径与个人贡献。
3. **能力边界**：英语仅注明本人提供的 CET-6 水平，不代表英语可作为工作语言；没有声称本人担任正式事件指挥、跨时区项目负责人或年度预算管理者。
4. 本包仅完成**本地静态文件构建**，未创建 GitHub 仓库，也未对外发布。
