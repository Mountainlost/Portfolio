# Portfolio® 中文作品集 / Studio v2

这是一个可直接部署到 GitHub Pages 的静态作品集网站。正式页是 `index.html`，可视化编辑器是 `studio.html`。

https://mountainlost.github.io/Portfolio/studio.html?utm_source=chatgpt.com

## 当前能力

- 中文为主的作品集页面；装饰性小字保留英文。
- 首页主标题为 `PORTFOLIO`，中段可保留描边视觉。
- 首页主视觉为普通图片 + WebGL 动效：缓慢液态流动、光泽漂移、鼠标视差。移动端自动降低强度，系统开启“减少动态效果”时自动回退静态图。
- 左侧实时预览，桌面 / 平板 / 手机三种视口。
- 点击模板文字可修改：内容、字体、字号、字重、行高、字距、颜色、对齐、透明度、层级、位置。
- 模板文字可直接在画布拖动并自动吸附；可隐藏（相当于删除），之后从“元素 / 图层”恢复。
- 可新增自由文本、自由图片、文本超链接；自由元素可拖动、复制、删除、修改层级与所在区域。
- 自由图片支持上传、圆角、裁切方式、透明度、点击链接。
- 作品项目数量不固定，可新增 / 删除 / 替换封面。
- 支持撤销 / 重做（当前编辑会话）。
- GitHub 设置完成后，“保存并发布”会上传新图片并更新 `content.js`，GitHub Pages 随仓库提交自动重新部署。

## 文件

- `index.html`：公开作品集
- `studio.html`：对照式可视化编辑器
- `content.js`：文字、项目、排版、自定义元素和主视觉动效配置
- `assets/`：默认视觉素材
- `assets/uploads/`：Studio 发布图片时自动创建 / 使用

## GitHub Pages 部署

1. 将本目录内容上传到仓库根目录。
2. GitHub 仓库 → Settings → Pages。
3. Source 选择 `Deploy from a branch`。
4. Branch 选择 `main`，目录选择 `/ (root)`。
5. 正式页：`https://用户名.github.io/仓库名/`
6. 编辑器：`https://用户名.github.io/仓库名/studio.html`

## Studio 的 GitHub 权限

建议创建 Fine-grained Personal Access Token，并且只授权当前作品集仓库：

- Repository permissions → Contents → Read and write

Token 只写入当前浏览器标签页的 `sessionStorage`，关闭标签页后消失，不会写进网站仓库。

## 主视觉动效

Studio → “首屏主视觉 / 动效”可以：

- 开启 / 关闭动效
- 调整流动强度
- 调整流动速度
- 调整鼠标视差
- 上传新的主视觉图片

动效代码完全在浏览器端运行，因此 GitHub Pages 支持，不需要云服务器。
