# 月亮与六便士 · 在线阅读与下载

简洁干净的《月亮与六便士》（The Moon and Sixpence）主题站点：全文在线阅读 + EPUB / TXT 下载。纯静态、零依赖，专为 Cloudflare Pages 部署准备。

## 文件结构

| 文件 | 说明 |
|---|---|
| `index.html` | 首页：内容简介、作者、摘录、下载 |
| `reader.html` | 在线阅读器：58 章目录、字号调节、深浅色、进度条 |
| `book/chapters.js` | 全书 58 章结构化数据（阅读器加载用） |
| `book/moon-and-sixpence.txt` | 全文纯文本（含 Project Gutenberg 版权信息） |
| `book/moon-and-sixpence.epub` | 自制电子书：带封面、章节目录，适配主流阅读器 |
| `_headers` | Cloudflare Pages 安全响应头与缓存策略 |
| `_redirects` | 路由规则 |

## 部署到 Cloudflare Pages

### 方式一：直接上传（最快）
1. Cloudflare Dashboard → Workers & Pages → Create → Pages
2. 选择 **Upload assets**
3. 把整个目录（含 `book/` 子目录）拖进去
4. Deploy，几秒后获得 `xxx.pages.dev` 域名

### 方式二：Git 集成
1. 本仓库已推送到 GitHub
2. Pages → Connect to Git → 选择本仓库
3. 构建配置：Framework preset `None`、Build command 留空、Build output directory `/`
4. Save and Deploy

### 方式三：Wrangler CLI
```bash
npm i -g wrangler
wrangler pages deploy . --project-name=moon-sixpence
```

## 功能特性

- 阅读器：章节目录下拉、上一章 / 下一章、键盘 ← / → 翻章、字号调节（15–24px）、阅读进度条、深浅色模式
- 动效：统一 `cubic-bezier(.22,1,.36,1)` 曲线；滚动渐入、章节切换淡入、段落错位入场
- 响应式：手机端自适应；尊重 `prefers-reduced-motion`
- 零依赖：无框架、无构建步骤

## 文本来源与版权

- 原文：*The Moon and Sixpence*, W. Somerset Maugham, 1919
- 来源：Project Gutenberg eBook #222（美国公有领域）
- 本站仅供个人学习交流，请勿用于商业用途
