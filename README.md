# Plex Swiper (Plex 首页轮播图美化)

这是一个为 Plex Web 客户端定制的 UI 美化脚本。它能自动识别你库中的推荐内容（电影或剧集），并在首页顶部生成一个丝滑、高颜值的 Swiper 轮播图。
参考项目地址：https://github.com/newday-life/emby-web-mod

---

## 📥 安装方式一：浏览器端（推荐）

这是最简单的安装方式。它不会修改你的 Plex 服务器文件，且支持官方 Web 端 (`app.plex.tv`)。

### 适用场景
* 使用 Chrome, Edge, Firefox, Safari 等桌面浏览器访问 Plex。
* 同时使用 `http://你的IP或域名:32400` 和 `https://app.plex.tv`。

### 安装步骤
1.  在浏览器中安装扩展程序 **Tampermonkey**。
2.  点击 [安装此脚本](https://greasyfork.org/zh-CN/scripts/560306-plex-swiper) 。
3.  刷新 Plex 网页即可生效。

---

## 🛠️ 安装方式二：服务端安装

该安装方式会使所有连接到你服务器的网页客户端（通过 IP/域名访问）都会自动加载此效果，**无需客户端安装油猴插件**。

### ⚠️ 局限性
1.  **不支持 app.plex.tv：** 通过 `app.plex.tv` 访问时，加载的是 Plex 官方托管的 Web 客户端，而不是你服务器上的文件。因此，服务端注入**仅在使用 `http://IP:32400` 或自定义域名**访问时生效。
2.  **更新会被覆盖：** 每次升级 Plex Media Server (Docker 重建或应用更新)，修改的文件会被还原，你需要重新操作一遍。
3.  **风险提示：** 修改服务器核心文件有风险，建议操作前备份 `index.html`。

### 安装步骤 (以 Linux/Docker 为例)

**1. 定位 Plex Web 目录**

通常位于：
`/usr/lib/plexmediaserver/Resources/Plug-ins-[版本号]/WebClient.bundle/Contents/Resources/`

群晖位于：
`/var/packages/PlexMediaServer/target/Resources/Plug-ins-[版本号]/WebClient.bundle/Contents/Resources/`

**2. 上传脚本文件**
将 `plex-swiper.js` 上传到上述目录中。

**3. 修改 index.html**
编辑同目录下的 `index.html` 文件。

找到文件末尾的 `<iframe>` 标签，在它**之前**添加脚本引用。

**正确的修改示例：**

```html
<script src="/web/js/main-xxxx.js" ...></script>
<script src="/web/plex-swiper.js"></script>
<iframe name="downloadFileFrame" style="display: none">
</body>
</html>
```

---

## 🌟 页面预览
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/61e0067f-fae8-4c7c-9985-f098ca5af3d9" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d6162567-a79c-4900-aec9-d346a3665ff4" />

