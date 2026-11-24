ESCAPE 更新交付包
版本：2026-11-24 / escape-v8

文件：
- index.html：页面、搜索、个人片库、18+会话确认
- manifest.webmanifest：PWA配置，图标统一指向 icons/ 目录
- sw.js：escape-v8缓存策略

部署要求：
1. 将三个文件放到 GitHub 仓库根目录，完整替换同名文件。
2. 保留仓库现有 icons/ 目录及以下文件：
   icon-192.png
   icon-512.png
   icon-maskable-192.png
   icon-maskable-512.png
   apple-touch-icon.png
3. 不要把图标移到根目录，也不要删除 icons/ 目录。
4. 等 GitHub Pages 部署完成后，先清除旧站点数据/Service Worker，再重新打开页面测试安装。

数据兼容：
- 保留 escape_library_v1
- 保留旧版 pfc_favorites 导入兼容
- 五类清单：收藏、稍后再看、已看、观影记录、搜索历史
- 导入采用按标题/TMDB ID 去重的合并策略，不覆盖原有数据

功能说明：
- 无 TMDB Key 时主搜索自动降级为所选引擎检索。
- TMDB 搜索失败时显示七大引擎备用入口。
- 平台搜索统一采用当前选定引擎 + site:官方域名。
- 18+专区用 sessionStorage 记录本次会话确认；这不是年龄验证。
- Service Worker 对单个缓存资源失败采用容错，不会因一个图标请求失败而整体安装失败。

限制：
- 本次交付未直接写入 GitHub。
- 本地静态检查不等于真实 Android Chrome 安装验证。
- BBC入口使用官方频道，并明确说明直播内容是否开放以频道显示为准；其他直播地址仍需在实际地区网络中逐项点验。
