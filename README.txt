# 私人影视中心（PWA）

## 文件
- `index.html`：完整网页与内容数据
- `manifest.webmanifest`：安装应用所需配置
- `sw.js`：离线缓存与 PWA service worker
- `icon-192.png`、`icon-512.png`：应用图标

## 部署
1. 在 GitHub 创建一个公开仓库，例如 `my-cinema`。
2. 将以上 5 个文件放在仓库根目录（不要放进子文件夹）。
3. 进入仓库 Settings → Pages。
4. 在 Build and deployment 中选择 Deploy from a branch；Branch 选 `main`，Folder 选 `/ (root)`，保存。
5. 等待部署完成，打开 `https://你的GitHub用户名.github.io/my-cinema/`。
6. 必须通过 HTTPS 地址访问，PWA 安装和离线缓存才会工作。

## 添加到设备
- Android：Chrome 打开网站 → 浏览器菜单 → “安装应用”或“添加到主屏幕”。
- iPhone/iPad：Safari 打开网站 → 分享 → “添加到主屏幕”。
- 电脑：支持的浏览器可能在地址栏或菜单中显示安装图标。

## 说明
- 此网页是官方平台导航，不托管影视文件；各平台免费内容及地区可用性会变化。
- 收藏保存在本机浏览器，不会自动跨设备同步。
- Service Worker 会缓存网页外壳；第三方影视/新闻网站需要联网访问。
- 修改网页后如设备仍显示旧版，可关闭已安装网页应用后重新打开；必要时清除该网站缓存或更新 `CACHE_NAME` 版本号。
