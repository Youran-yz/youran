# 书库 · Moon Library

一间简洁干净的私人书库站点：在线阅读 + 下载，纯静态、零依赖，专为 Cloudflare Pages 部署准备。

## 在架书目

| 书目 | 作者 | 内容 |
|---|---|---|
| 《月亮与六便士》 | 毛姆 | 中英双语全文在线阅读 + EPUB / TXT 下载 |
| 《活着》 | 余华 | 作品导览（简介 / 作者 / 摘录）+ 正版阅读入口 |

## 文件结构

| 文件 | 说明 |
|---|---|
| `index.html` | 书库首页（书目卡片，手机 / 电脑自适应） |
| `moon.html` | 《月亮与六便士》详情页 |
| `huozhe.html` | 《活着》导览页 |
| `reader.html` | 在线阅读器：中英切换、章节目录、字号调节、进度条 |
| `book/moon-en.js` | 《月亮与六便士》英文全文（58 章数据） |
| `book/moon-zh.js` | 中文译文（58 章数据，AI 翻译整理） |
| `book/moon-and-sixpence.txt` | 英文全文纯文本 |
| `book/moon-and-sixpence.epub` | 英文版电子书（带封面、目录） |
| `book/moon-zh.epub` | 中文版电子书（带封面、目录） |
| `_headers` / `_redirects` | Cloudflare Pages 配置 |

## 部署到 Cloudflare Pages

### 方式一：Git 集成（推荐）
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git
2. 选择本仓库
3. 构建配置：Framework preset `None`、Build command 留空、Build output directory `/`
4. Save and Deploy

### 方式二：直接上传
把整个目录（含 `book/` 子目录）拖进 **Upload assets**，或使用打包好的 zip。

### 方式三：Wrangler CLI
```bash
npm i -g wrangler
wrangler pages deploy . --project-name=moon-sixpence
```

## 功能特性

- 首页：书库式卡片布局，手机端自动切换为横向列表样式
- 阅读器：中 / EN 切换、章节目录、键盘 ← → 翻章、字号调节（15–24px）、阅读进度条、深浅色模式、手机底部快捷翻章栏
- 动效：统一 `cubic-bezier(.22,1,.36,1)` 曲线；滚动渐入、章节切换淡入、段落错位入场
- 响应式：自动识别手机 / 电脑，适配不同布局；尊重 `prefers-reduced-motion`
- 零依赖：无框架、无构建步骤

## 说明与版权

- 《月亮与六便士》英文原文（W. Somerset Maugham, 1919）属公有领域，源自 Project Gutenberg eBook #222；中文译文由 AI 翻译整理，仅供学习参考。
- 《活着》（余华）仍在版权保护期内，本站不存储、不提供全文，仅提供作品导览与正版平台链接。
- 全站仅供个人学习交流，请勿用于商业用途。
