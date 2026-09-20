# PlainTab Custom v6

基于 PlainTab `v3.1.4` 制作的独立非官方定制版。

> [!IMPORTANT]
> 本仓库并非 PlainTab 上游官方发布版本。

## 下载与安装

1. 下载仓库中的 [`PlainTab-3.1.4修改版v6.zip`](./PlainTab-3.1.4修改版v6.zip)。
2. 将压缩包解压到一个固定目录。
3. 在 Chrome 或 Edge 中打开扩展管理页面。
4. 开启“开发者模式”，选择“加载已解压的扩展程序”。
5. 选择刚刚解压的项目目录。

## 来源与许可

- 上游项目：[kaininx/PlainTab](https://github.com/kaininx/PlainTab)
- 上游作者：[Kaelri（@kaininx）](https://github.com/kaininx)
- 修改基线：[PlainTab v3.1.4](https://github.com/kaininx/PlainTab/releases/tag/v3.1.4)
- 许可证：MIT，原版权声明与许可条款见 [LICENSE](./LICENSE)

本仓库保留了上游项目的 MIT 许可证和版权声明。感谢原作者开发并开源 PlainTab。

## 本改版的主要变化

### 1. 书签栏深度重构与原生化

- 顶部书签栏容器改为透明样式，取消底部边框线条。
- 每个书签项采用独立的半透明毛玻璃药丸设计。
- 高级设置新增 **Bookmarks opacity（书签背景不透明度）** 滑块与数值框，支持实时平滑调节。
- 增加 HTML5 长按拖拽排序，并通过 `chrome.bookmarks.move` 将顺序同步到 Chrome 原生书签树。
- 修复设置加载时提前保存导致图标透明度和书签透明度被重置的问题。

### 2. 搜索框体验与交互优化

- 新标签页打开后自动聚焦中央搜索框，可直接键入内容搜索。
- 为“悬停时显示搜索框”模式加入 `:focus-within` 支持，输入或聚焦时搜索框会自动显示并保持可见。
- 移除 `Search the web` 等默认占位提示，减少选中和输入时的视觉干扰。

### 3. 网络 URL 壁纸与混合轮播

- 设置面板新增独立的 **URL image** 入口，可直接添加网络图片链接。
- URL 图片可与本地上传图片混合存入画廊，并在打开新标签页时按顺序循环切换。
- 统一 URL 图片与本地图片的缩略图管理，并支持单项删除。
- 修复已有壁纸后“添加壁纸”入口消失的问题，改为“+ 本地壁纸”和“+ URL 图片”两个按钮。
- 优化 `js/preload.js` 对网络图片的预加载，减少新标签页打开时的黑屏和明暗闪烁。

### 4. 架构与兼容性修复

- 移除 `manifest.json` 中不适用的 `search` 权限声明。
- 调整冲突的内容安全策略，避免内联 CSS 变量（如 `--bm-bg-opacity`、`--icon-opacity`）导致页面白屏。

## 版本说明

此版本继续使用 `3.1.4` 作为上游基线版本号，并以 `Custom v6` 标识本定制版本。它没有合并 PlainTab `3.2.x` 的后续更新。
