# 雷霆战机 · 手机网页版（PWA）

三关竖版飞机大战，已适配手机触屏，可添加到主屏幕，断网也能玩。

## 文件（全部在根目录，方便直接上传）

```
index.html               游戏本体（单文件，含画面与音效）
manifest.webmanifest     PWA 应用信息
sw.js                    Service Worker，离线缓存
icon-192.png             手机桌面图标
icon-512.png             高清图标
icon-maskable-512.png    安卓自适应图标
apple-touch-icon.png     iPhone 主屏幕图标
favicon.png              浏览器标签图标
.nojekyll                告诉 GitHub Pages 不要用 Jekyll 处理
README.md                本说明
```

## 上传到 GitHub Pages（推荐）

1. 注册/登录 <https://github.com>
2. 右上角 **+** → **New repository**
3. 仓库名填 `plane-war`，选择 **Public**，点 **Create repository**
4. 在新仓库页面点 **Add file** → **Upload files**
5. 把本文件夹里的**所有文件**全选，拖进上传区域（不要只传 zip）
6. 点 **Commit changes**
7. 进入仓库 **Settings** → 左侧 **Pages**
8. **Build and deployment** → Source 选 **Deploy from a branch**
9. Branch 选 **main**，目录选 **/ (root)**，点 **Save**
10. 等 1～2 分钟，页面顶部会出现网址：

```
https://你的用户名.github.io/plane-war/
```

手机浏览器打开这个网址即可玩；浏览器菜单 → **添加到主屏幕**，以后从桌面图标进入就是全屏。

> 注意：免费账号的 Pages 需要仓库是 **Public**。如果仓库名取 `你的用户名.github.io`，网址会变成 `https://你的用户名.github.io/`。

## 上传到 Netlify（不用 GitHub）

1. 打开 <https://app.netlify.com/drop>
2. 把整个文件夹或 `plane-war-mobile.zip` 拖进去
3. 立即得到 HTTPS 网址，手机打开即可

## 局域网本地预览

在本文件夹执行：

```bash
python -m http.server 8080
```

手机连同一个 Wi-Fi，访问 `http://电脑局域网IP:8080`。  
局域网 HTTP 不能安装 PWA / 注册 Service Worker，但游戏本身可玩。

## 直接玩单文件版

不想部署的话，把外面的 `plane-war.html` 发到手机，用浏览器打开即可。  
没有“添加到主屏幕”和离线缓存，其余完全一样。

## 操作

- **移动**：手指拖动；电脑用鼠标拖动或 WASD / 方向键
- **开火**：自动
- **炸弹**：B / K，或右下角按钮
- **暂停**：P / ESC，或右下角按钮
- **音效**：M，或右下角按钮

## 说明

- PWA 安装与 Service Worker 需要 **HTTPS** 或 **localhost**（GitHub Pages、Netlify 都满足）。
- 画面会按屏幕比例自动拉长，手机竖屏基本铺满。
- 最高分存在浏览器 localStorage。
