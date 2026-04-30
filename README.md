# 吱吱的剧笺手札 · GitHub Pages 部署包

这是一个纯静态网页版本，适合直接部署到 GitHub Pages。

## 文件结构

```text
.
├── index.html
├── .nojekyll
├── assets/
│   └── README.md
├── data/
│   └── presets.json
└── docs/
    └── update-presets.md
```

## 使用方式

1. 把 `index.html` 放在 GitHub 仓库根目录。
2. 把素材图片放进 `assets/` 文件夹，文件名保持 `1.png` 到 `10.png`。
3. 在 GitHub 仓库设置里开启 Pages。
4. Source 选择 `Deploy from a branch`。
5. Branch 选择 `main`，Folder 选择 `/root`。
6. 保存后等待 Pages 自动发布。

## 数据说明

网页仍使用浏览器本地 `localStorage` 保存用户数据。

这意味着：

- 用户写的内容不会上传到 GitHub。
- 每个用户的数据只存在自己的浏览器里。
- 作者更新 `index.html` 不会自动覆盖用户已经保存的本地内容。
- 从本地文件版迁移到线上版时，需要先在本地版导出 JSON，再在线上版导入 JSON。

## 更新页面

之后你只需要替换仓库里的 `index.html`，GitHub Pages 会自动重新部署。

## 更新作者预设

当前页面仍以内置 `defaultState` 作为首次打开的默认内容。`data/presets.json` 是预留给后续“作者预设更新”机制使用的结构化文件。
