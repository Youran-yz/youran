# Nova 网站模板

简洁干净的纯静态单页模板，专为 Cloudflare Pages 部署准备。

## 文件

| 文件 | 说明 |
|---|---|
| `index.html` | 整站页面（HTML + CSS + JS 全内联，零依赖） |
| `_headers` | Cloudflare Pages 安全响应头 |
| `_redirects` | 路由 / 重定向规则 |

## 部署到 Cloudflare Pages

### 方式一：直接上传（最快）
1. 打开 Cloudflare Dashboard → Workers & Pages → Create → Pages
2. 选择 **Upload assets**
3. 把 `index.html`、`_headers`、`_redirects` 拖进去
4. 点 Deploy，几秒后就有一个 `xxx.pages.dev` 域名

### 方式二：Git 集成（可自动更新）
1. 把这三个文件推到 GitHub 仓库
2. Pages → Connect to Git → 选仓库
3. 构建配置：
   - Framework preset：`None`
   - Build command：留空
   - Build output directory：`/`
4. Save and Deploy

### 方式三：Wrangler CLI
```bash
npm i -g wrangler
wrangler pages deploy . --project-name=nova
```

## 自定义

- **主题色**：改 `:root` 里的 `--accent`（`--accent-soft` 是它的浅色底）
- **文字内容**：直接搜 HTML 里的中文替换
- **深色模式**：自动跟随系统，右上角按钮可手动切换，记忆存在 localStorage
- **字体**：用了 Google Fonts 的 Inter，国内可换成 `system-ui` 提速

## 内置特性

- 滚动渐入动画（IntersectionObserver，带错位延迟）
- 吸顶导航，滚动时自动加分隔线
- 响应式：手机端折叠菜单
- 深浅双主题 + 本地记忆
- 尊重 `prefers-reduced-motion`（系统开启减少动效时自动关闭动画）
- 无障碍：语义化标签、aria-label、键盘可用
