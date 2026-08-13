# PhantomRepo 幻影源

> 精选优质越狱插件，专注系统优化与界面美化

## 📱 添加源

### Cydia / Sileo / Zebra
```
https://phantomrepo.github.io
```

## 🚀 部署到 GitHub Pages

### 方法一：直接上传

1. Fork 本仓库
2. 进入 Settings → Pages
3. Source 选择 `main` 分支，根目录
4. 等待部署完成，地址为 `https://你的用户名.github.io/PhantomRepo/`

### 方法二：本地构建后上传

```bash
# 克隆仓库
git clone https://github.com/你的用户名/PhantomRepo.git
cd PhantomRepo

# 添加新插件后更新 Packages
dpkg-scanpackages debs / > Packages
gzip -k -f Packages

# 提交并推送
git add .
git commit -m "Add new tweak"
git push
```

## 📁 目录结构

```
PhantomRepo/
├── Release              # 源元信息
├── Packages             # 包索引（明文）
├── Packages.gz          # 包索引（gzip压缩）
├── CydiaIcon.png        # 源图标（96x96 / 128x128）
├── index.html           # 源主页
├── README.md
├── debs/                # .deb 插件包
│   ├── com.phantom.phantomstatusbar_2.3.1_iphoneos-arm64.deb
│   ├── com.phantom.ccenhancer_1.8.0_iphoneos-arm64.deb
│   └── ...
├── depictions/          # 插件详情页
│   ├── phantomstatusbar.html    # Cydia Depiction
│   ├── phantomstatusbar.json    # Sileo Depiction
│   └── ...
└── assets/              # 图片资源
    ├── icon_statusbar.png
    └── ...
```

## 🛠 添加新插件

### 1. 准备 deb 包
```bash
# 打包插件
dpkg-deb -b your-tweak-folder com.your.tweak_1.0_iphoneos-arm64.deb
```

### 2. 放入 debs 目录
```bash
mv com.your.tweak_1.0_iphoneos-arm64.deb debs/
```

### 3. 更新 Packages 索引
```bash
dpkg-scanpackages debs / > Packages
gzip -k -f Packages
```

### 4. 创建 Depiction 页面
- 在 `depictions/` 下创建对应的 HTML 和 JSON 文件
- 添加截图、描述、变更日志等

### 5. 提交推送
```bash
git add .
git commit -m "Add YourTweak v1.0"
git push
```

## 📋 插件列表

| 插件 | 版本 | 分类 | 描述 |
|------|------|------|------|
| 幻影状态栏 | v2.3.1 | System | 状态栏全面美化 |
| 控制中心增强 | v1.8.0 | System | 20+快捷开关 |
| 通知中心重构 | v3.0.2 | UI | 卡片式通知 |
| 应用锁Pro | v2.1.0 | Security | 指纹/面容锁应用 |
| 文件夹增强 | v1.5.3 | UI | 无限文件夹嵌套 |
| 手势导航 | v2.0.1 | System | 全面屏手势 |

## 🔗 联系方式

- Twitter: @PhantomRepo
- Telegram: @PhantomRepo
- Email: admin@phantomrepo.com

## ⚠️ 免责声明

本源仅供学习研究使用，请遵守当地法律法规。使用插件造成的任何问题由用户自行承担。

---

**PhantomRepo © 2024**
