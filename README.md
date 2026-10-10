# Portfolio® 中文作品集网站

这是一个纯静态、响应式的个人作品集网站，包含：

- `index.html`：正式网站
- `studio.html`：对照编辑页（左侧最终效果，右侧可编辑内容）
- `content.js`：所有可编辑文字和项目数据
- `assets/`：示例作品图片与以后上传的图片
- `.nojekyll`：让 GitHub Pages 直接按静态文件发布

## 1. 本地查看

直接打开 `index.html` 可以看正式网站。打开 `studio.html` 可以进入对照编辑页。

更推荐用本地服务器预览：

```bash
python -m http.server 8000
```

浏览器访问：

- 正式页：`http://localhost:8000/index.html`
- 编辑页：`http://localhost:8000/studio.html`

## 2. GitHub Pages 部署

1. 新建一个 GitHub 仓库，例如 `portfolio`。
2. 把这个文件夹里的所有文件上传到仓库 `main` 分支根目录。
3. GitHub 仓库进入 `Settings → Pages`。
4. `Build and deployment` 选择 `Deploy from a branch`。
5. Branch 选择 `main`，文件夹选择 `/ (root)`，保存。
6. GitHub 会生成网站地址，通常是 `https://用户名.github.io/仓库名/`。

CSS、JavaScript、Canvas 动效都可以直接在 GitHub Pages 上运行，不需要云服务器。GitHub Pages 不支持 PHP / Python 等服务端程序，但本项目不依赖这些功能。

## 3. 使用“对照编辑页”

打开正式网站地址后，在网址后加 `studio.html`，例如：

`https://用户名.github.io/portfolio/studio.html`

页面左侧是网站最终效果，右侧是内容表单。修改文字会实时显示在左侧；替换图片会先本地预览。

点击右上角 **“保存并发布”** 时，工作台会：

1. 把新图片上传到仓库的 `assets/uploads/`。
2. 更新 `content.js`。
3. 向 `main` 分支创建一次 commit。
4. GitHub Pages 检测到分支变化后自动重新发布正式网站。

## 4. 第一次发布需要连接 GitHub

在 `studio.html` 右上角点击 **“GitHub 设置”**，填写：

- GitHub 用户名
- 仓库名
- 分支（默认 `main`）
- 正式网站地址（可选）
- GitHub Fine-grained Personal Access Token

Token 建议只授权给这个作品集仓库，并只开启 **Contents: Read and write** 权限。

安全设计：Token 只保存在浏览器当前标签页的 `sessionStorage`，不会写进网页文件或 GitHub 仓库。关闭标签页后 Token 会消失，下次需要重新输入。

## 5. 中文内容位置

所有正式网站内容都在 `content.js`。即使以后不使用编辑器，也可以直接修改这个文件。

目前可编辑：

- 首屏文字
- 精选作品区文字
- 6 个项目的名称、分类、年份、介绍、标签和图片
- 创作观点
- 我的实践
- 关于我
- 联系信息
- 导航和页脚

## 6. 图片建议

推荐作品封面使用 JPG / WebP / PNG，比例接近 **4:3**。为了加载速度，建议单张图片控制在 1–2 MB 以内。

## 7. 发布延迟

编辑页“发布成功”表示内容已经提交到 GitHub。GitHub Pages 仍需要短暂时间完成重新发布，因此正式网址不会保证在点击按钮后瞬间更新。
