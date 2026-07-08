# 部署指南 | Deployment Guide

本仓库可直接部署到 GitHub + Vercel。

---

## 方式一：手动推送到 GitHub 并导入 Vercel（推荐）

### 第 1 步：在 GitHub 创建仓库

1. 打开 https://github.com/new
2. 仓库名建议：`ye-qiaoying-portfolio`（或你喜欢的名字）
3. 选择 **Public**（Vercel Hobby 版只能免费部署 Public 仓库，Pro 可部署 Private）
4. 不要勾选 README、.gitignore、license
5. 点击 **Create repository**

### 第 2 步：推送本地代码

复制仓库地址后，在本项目根目录执行：

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

示例：

```bash
git remote add origin https://github.com/yeqiaoying/ye-qiaoying-portfolio.git
git branch -M main
git push -u origin main
```

### 第 3 步：导入 Vercel

1. 打开 https://vercel.com/new
2. 选择刚刚创建的 GitHub 仓库
3. 在配置页确认：
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - 如果未自动识别，可手动输入
4. 点击 **Deploy**

### 第 4 步：等待部署完成

Vercel 会自动：
- 安装依赖
- 运行 `npm run build`
- 部署 `dist/` 目录

完成后会获得类似 `https://ye-qiaoying-portfolio.vercel.app` 的链接。

---

## 方式二：使用 Vercel CLI（适合开发者）

```bash
# 全局安装 Vercel CLI
npm i -g vercel

# 登录
vercel login

# 在项目根目录执行
vercel

# 按提示选择或新建项目，后续更新直接运行
vercel --prod
```

---

## 常见问题

### 1. 图片没有显示

确保 `public/images/` 目录已推送到 GitHub。Vite 构建时会自动复制 `public/` 到 `dist/`。

### 2. 路由 404

本项目为单页应用（SPA），刷新子路径需要 Vercel 回退到 `index.html`。`vercel.json` 已包含此配置，如使用其他平台请自行添加：

```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

### 3. 域名自定义

在 Vercel 项目设置 → Domains 中添加自己的域名，按提示配置 DNS 即可。

---

## 本地预览命令

```bash
cd /workspace/app-cuqsl4lmrif5
npm run build
npm run preview
```

预览地址：http://localhost:4173
