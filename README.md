# 叶巧莹个人网站 | Ye Qiaoying Portfolio

一个复古杂志拼贴风格的个人品牌静态网站。

## 技术栈
- React 18
- TypeScript
- Vite
- Tailwind CSS
- Lucide React

## 本地开发

```bash
pnpm install
pnpm dev
```

## 构建

```bash
pnpm build
```

构建产物位于 `dist/` 目录。

## 部署

### Vercel 部署

1. 将代码推送到 GitHub 仓库
2. 在 Vercel 中导入该仓库
3. 构建命令：`npm run build`
4. 输出目录：`dist`
5. 框架预设：Vite

## 自定义内容

所有展示内容位于 `src/data.ts`，直接替换文本和图片路径即可。
