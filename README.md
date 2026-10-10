# Portfolio® 中文作品集网站

这是一个纯静态、响应式的个人作品集网站，包含：

- `index.html`：正式网站
- `studio.html`：对照编辑页（左侧实时画布，右侧编辑器）
- `content.js`：文字、排版参数、拖动位置和项目数据
- `assets/`：作品图片与首屏主视觉
- `.nojekyll`：让 GitHub Pages 直接发布静态文件

## 对照编辑器现在支持

打开 `studio.html` 后：

1. **点击左侧任意可编辑文字**，右侧会出现该元素的专属编辑面板。
2. 可以修改：文字内容、字体、字号、行高、字间距。
3. **按住左侧文字直接拖动**，位置按 8px 网格吸附，并会对齐页面容器、页面中线和其它文字的边缘 / 中心。
4. 右侧可以精确输入 X / Y 偏移，也可以一键恢复默认位置或默认排版。
5. 首屏主图可以直接上传替换。
6. 项目封面仍然可以逐个上传替换。
7. 所有修改在左侧实时预览，点击“保存并发布”后才会写入 GitHub。

## 本地查看

直接打开 `index.html` 可以看正式网站。为了让 iframe、上传和浏览器存储行为与线上一致，更推荐用本地服务器：

```bash
python -m http.server 8000
```

浏览器访问：

- 正式页：`http://localhost:8000/index.html`
- 编辑页：`http://localhost:8000/studio.html`

## GitHub Pages 部署

1. 新建一个 GitHub 仓库，例如 `portfolio`。
2. 把这个文件夹里的**全部文件**上传到仓库 `main` 分支根目录。
3. 仓库进入 `Settings → Pages`。
4. `Build and deployment` 选择 `Deploy from a branch`。
5. Branch 选择 `main`，文件夹选择 `/ (root)`，保存。
6. 网站地址通常是 `https://用户名.github.io/仓库名/`。

CSS、JavaScript、图片动画和当前编辑器都可以直接在 GitHub Pages 上运行，不需要云服务器。

## 第一次连接 GitHub

打开线上 `studio.html`，点击右上角 **GitHub 设置**，填写：

- GitHub 用户名
- 仓库名
- 分支（默认 `main`）
- 正式网站地址（可选）
- GitHub Fine-grained Personal Access Token

Token 建议只授权给这个作品集仓库，并只开启 **Contents: Read and write**。

Token 只保存在当前浏览器标签页的 `sessionStorage`，不会写进网站文件或仓库。关闭标签页后会消失。

## 保存并发布

点击 **保存并发布** 后，编辑器会：

1. 把新首屏主图 / 项目图片上传到 `assets/uploads/`。
2. 把文字、字体参数和拖动位置写入 `content.js`。
3. 提交到 GitHub `main` 分支。
4. GitHub Pages 自动重新部署正式站点。

## 图片建议

- 首屏主图：建议宽屏 JPG / WebP，比例约 16:9～21:9，2 MB 以内。
- 项目封面：建议 JPG / WebP / PNG，比例接近 4:3，单张 1–2 MB 以内。

## 更新已有 GitHub 网站

如果仓库里已经有旧版，请至少替换：

- `index.html`
- `studio.html`
- `content.js`
- `README.md`
- `assets/hero-art.webp`

然后 Commit。GitHub Pages 会自动重新部署。
