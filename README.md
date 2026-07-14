# 即念 — 记住生命中每一个重要时刻

> Liquid Glass 风格的全平台纪念日 / 备忘录 / 好友生日管理应用

<p align="center">
  <img src="assets/images/app_icon.png" width="120" alt="即念图标"/>
</p>

## 应用简介

即念是一款跨平台个人生活管理应用，帮助你记录和提醒生命中每一个重要的日子。支持纪念日倒数/正数、好友生日（公历/农历）、富文本备忘录与待办清单，数据通过 Supabase 云端同步，所有平台共享同一份数据。

- **包名**: `com.ouiuan.jinian_app`
- **版本**: 1.0.0+1
- **最低 Android**: API 21 (Android 5.0)
- **支持平台**: Android / iOS / Web / Windows / macOS / Linux

## 功能

| 模块 | 功能 |
|------|------|
| 📅 **纪念日** | 正数/倒数双模式、分类图标、里程碑提醒（100天/520天等）、重复周期 |
| 🎂 **好友生日** | 公历/农历双支持、关系标签、排序筛选、倒计时 |
| 📝 **备忘录** | flutter_quill 所见即所得富文本编辑、待办清单（JSON 结构化存储） |
| 🔔 **通知** | 本地通知调度、应用关闭后仍可推送、点击跳转 |
| 🧩 **小组件** | 今日概览、近期事件统计、待办进度 |
| 🎨 **Liquid Glass UI** | 40px 高斯模糊、多层阴影、内发光渐变、靛紫粉配色 |
| ☁️ **云端同步** | Supabase 后端、离线优先、登录后自动同步 |
| 📦 **应用内更新** | 基于 GitHub Releases 自动检查更新、下载安装 |
| 🔒 **安全加固** | ProGuard/R8 混淆、SSL Pinning、请求签名、加密存储 |
| 🌐 **全平台** | iOS / Android / Web / Windows / macOS / Linux |

## 技术栈

| 层级 | 技术 |
|------|------|
| 框架 | Flutter 3.38 (Dart 3.10) |
| 后端 | Supabase (Auth + PostgreSQL + Realtime) |
| 状态管理 | Riverpod |
| 路由 | go_router |
| 本地存储 | SQLite (原生) / SharedPreferences (Web) |
| 通知 | flutter_local_notifications |
| 富文本 | flutter_quill 11.x |
| 本地化 | flutter_localizations (中文) |
| 安全存储 | flutter_secure_storage (Android Keystore) |
| 网络安全 | 自建 SSL Pinning + 请求签名 |
| 自动更新 | GitHub Releases API + http |

## UI 设计风格 — Liquid Glass（毛玻璃）

即念采用 **Liquid Glass** 设计语言，灵感源自 Apple 的玻璃质感与现代新拟物风格，通过多层半透明叠加、高斯模糊和柔和光影营造出轻盈通透的视觉体验。

### 设计原则

| 原则 | 说明 |
|------|------|
| **通透性** | 大面积半透明背景，让底层色彩和内容隐约可见 |
| **层次感** | 多层阴影 + 内发光渐变，卡片悬浮于背景之上 |
| **柔和过渡** | 靛紫粉渐变主色调，深/浅双模式无缝切换 |
| **呼吸感** | 大圆角（16-24px）、宽松间距、轻量化字体 |

### 色彩系统

| 色组 | 色值 | 用途 |
|------|------|------|
| **Primary** | `#7B61FF` | 主色、按钮、选中态 |
| **Primary Accent** | `#C084FC` | 强调色、渐变辅助 |
| **Light BG** | `#F0F4F8` / `#E8EDF2` | 浅色模式背景 |
| **Dark BG** | `#0D1117` / `#161B22` | 暗色模式背景 |
| **Danger** | `#FF6B6B` | 删除、错误 |
| **Success** | `#51CF66` | 完成、待办打勾 |
| **Warning** | `#FFD43B` | 提醒、进度 |
| **Info** | `#4DABF7` | 链接、次要信息 |
| **Orange** | `#FF922B` | 生日模块专用 |

毛玻璃透明色：

| 色值 | 用途 |
|------|------|
| `White 55%` | 浅色模式卡片背景 |
| `White 6-12%` | 暗色模式卡片背景 |
| `White 30-40%` | 浅色模式卡片边框 |
| `White 8%` | 暗色模式卡片边框 |

### 渐变组合

| 名称 | 渐变 | 用途 |
|------|------|------|
| Primary | `#7B61FF → #6366F1` | 主按钮、重要元素 |
| Warm | `#FF6B6B → #FF922B` | 删除、警告 |
| Cool | `#4DABF7 → #7B61FF` | 信息、链接 |
| Nature | `#51CF66 → #20C997` | 完成、成功 |

### 核心组件

| 组件 | 文件 | 特性 |
|------|------|------|
| **GlassCard** | `lib/shared/widgets/glass_card.dart` | 20px 高斯模糊 + 多层阴影 + 内发光渐变 + 24px 圆角 |
| **GlassButton** | `lib/shared/widgets/glass_button.dart` | 渐变背景 + 白色半透明边框 + 阴影投影 |
| **GlassTextField** | `lib/shared/widgets/glass_text_field.dart` | 半透明填充 + 聚焦紫色边框 + 圆角 16px |
| **GlassBottomNav** | `lib/shared/widgets/glass_bottom_nav.dart` | 毛玻璃导航栏 + 选中动效 |
| **CountdownTile** | `lib/shared/widgets/countdown_tile.dart` | 倒计时卡片 + 渐变背景 |
| **EmptyState** | `lib/shared/widgets/empty_state.dart` | 空状态插画 + 引导文字 |

### 主题系统

```dart
// lib/core/theme/
├── app_colors.dart      # 色彩常量（80 行，含渐变/图标色板）
├── app_theme.dart       # Material3 主题配置（238 行，完整组件风格覆盖）
└── theme_provider.dart  # Riverpod 状态管理（深色/浅色/跟随系统）
```

主题模式支持：
- 🌓 **跟随系统**：自动匹配系统深色模式设置
- ☀️ **浅色模式**：白色基底 + 高透明度玻璃
- 🌙 **深色模式**：深灰基底 + 低透明度玻璃

### 排版

- 字体：**PingFang SC**（苹方，iOS/macOS 原生中文字体，Android 回退到系统默认）
- 标题：24-36px，Weight 700
- 正文：14-16px，Weight 400，行高 1.5-1.6
- 辅助文字：12-13px，降低透明度

### 文件清单

```
lib/
├── core/theme/
│   ├── app_colors.dart           # 色彩系统
│   ├── app_theme.dart            # 主题配置
│   └── theme_provider.dart       # 主题状态管理
├── shared/widgets/
│   ├── glass_card.dart           # 毛玻璃卡片
│   ├── glass_button.dart         # 毛玻璃按钮
│   ├── glass_text_field.dart     # 毛玻璃输入框
│   ├── glass_bottom_nav.dart     # 毛玻璃底部导航
│   ├── countdown_tile.dart       # 倒计时组件
│   └── empty_state.dart          # 空状态组件
```

## 快速开始

### 环境要求

- Flutter SDK >= 3.10
- Dart SDK >= 3.10
- Android Studio / Xcode（移动端）
- Chrome（Web 端）

### 克隆与安装

```bash
git clone <仓库地址>
cd 即念
flutter pub get
```

### 配置 Supabase

1. 在 [supabase.com](https://supabase.com) 创建项目
2. 在 SQL Editor 执行 `supabase/migrations/20240101000000_init.sql`
3. 修改 `lib/core/constants/app_constants.dart` 中的 URL 和 Anon Key
4. 在 Supabase Authentication → Settings 中启用 Email 登录

### 运行

```bash
# Web 端
flutter run -d chrome --web-port=3000

# Android 端
flutter run -d android

# iOS 端
flutter run -d ios

# 桌面端
flutter run -d windows
flutter run -d macos
```

## 项目结构

```
即念/
├── lib/
│   ├── main.dart                    # 应用入口（初始化 DB/Supabase/通知/更新服务）
│   ├── app.dart                     # MaterialApp.router 根组件
│   ├── core/
│   │   ├── theme/                   # Liquid Glass 主题系统
│   │   ├── router/                  # go_router 路由表
│   │   ├── constants/               # 应用常量（Supabase URL/Key）
│   │   ├── services/                # 更新服务、安全 HTTP 客户端、安全存储
│   │   └── utils/                   # 通知调度、日期工具
│   ├── data/
│   │   ├── datasources/local/       # SQLite + SharedPreferences
│   │   ├── datasources/remote/      # Supabase REST + Realtime
│   │   ├── models/                  # freezed 数据模型
│   │   └── repositories/            # 离线优先仓库 + 同步引擎
│   ├── features/
│   │   ├── auth/                    # 登录/注册
│   │   ├── home/                    # 首页仪表盘
│   │   ├── anniversary/             # 纪念日（列表/表单/详情）
│   │   ├── birthday/                # 好友生日
│   │   ├── memo/                    # 备忘录（笔记/待办）
│   │   ├── notification/            # 通知设置
│   │   ├── settings/                # 设置页（含检查更新）
│   │   └── widget/                  # 桌面小组件
│   └── shared/widgets/              # Liquid Glass 通用组件
├── assets/images/                   # 应用图标资源
├── supabase/migrations/             # 数据库初始化 SQL
├── web/                             # PWA 配置
├── android/                         # Android 原生
│   ├── app/
│   │   ├── build.gradle.kts         # 签名 + ProGuard 配置
│   │   ├── proguard-rules.pro       # 混淆规则
│   │   └── src/main/res/xml/        # 安全配置（network_security_config 等）
│   └── gradle.properties            # 含 android.overridePathCheck=true
├── ios/                             # iOS 原生
└── pubspec.yaml
```

---

## 打包发布

### 1. 生成签名密钥（仅需一次）

```bash
keytool -genkey -v -keystore d:\ouiuan\即念\android\key.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias jinian-key
```

按提示设置密码（建议 12 位以上，混合大小写+数字+符号）。

### 2. 创建签名配置文件

在 `android/key.properties` 中创建：

```properties
storeFile=../key.jks
storePassword=你设置的密钥库密码
keyPassword=你设置的密钥密码
keyAlias=jinian-key
```

### 3. 构建正式版 APK（混淆 + 安全加固）

```bash
cd d:\ouiuan\jinian
flutter build apk --release --obfuscate --split-debug-info=./symbols
# 输出: build/app/outputs/flutter-apk/app-release.apk
```

`--obfuscate` 启用 Dart 代码混淆，`--split-debug-info` 将调试符号分离到 `./symbols` 目录。

> **重要**：`symbols/` 目录包含调试符号表，发布后如有崩溃报告需要用它对混淆后的堆栈进行还原。该目录已加入 `.gitignore`，请妥善保管。

### 4. 构建 Android App Bundle（发布 Google Play）

```bash
flutter build appbundle --release --obfuscate --split-debug-info=./symbols
# 输出: build/app/outputs/bundle/release/app-release.aab
```

### 5. iOS

```bash
flutter build ios --release
# 然后用 Xcode 打开 ios/Runner.xcworkspace 进行 Archive
```

### 6. Web

```bash
flutter build web --release
# 输出: build/web/
```

---

## 应用内自动更新（GitHub Releases）

应用启动 5 秒后自动检查 GitHub Releases 是否有新版本，发现更新后弹窗提示下载安装。设置页也可手动触发检查。

### 前置准备

1. 在 GitHub 创建仓库 `jinian_releases`（Public）
2. 修改 `lib/core/services/update_service.dart` 第 64-65 行：

```dart
static const String _owner = 'ouiuan';          // GitHub 用户名
static const String _repo = 'jinian_releases';  // 仓库名
```

### 发布新版本流程

**Step 1 — 更新版本号**

修改 `pubspec.yaml`，build 号 +1：

```yaml
version: 1.0.0+2   # 之前是 1.0.0+1
```

**Step 2 — 构建 APK**

```bash
cd d:\ouiuan\jinian
flutter build apk --release --obfuscate --split-debug-info=./symbols
```

**Step 3 — 创建 GitHub Release**

打开 https://github.com/ouiuan/jinian_releases/releases/new

| 字段 | 填写内容 |
|------|----------|
| **Tag version** | `v1.0.0+2`（与 pubspec.yaml 一致） |
| **Release title** | `v1.0.0+2` 或 `首次发布` |
| **Describe** | 更新日志，需要强制更新时加 `[force]` |

将 `build/app/outputs/flutter-apk/app-release.apk` 拖拽到 📎 区域，点击 **Publish release**。

**示例 Release：**

```
Tag:      v1.0.0+1
Title:    首次发布

描述:
- 纪念日、生日、备忘录功能
- 云端数据同步
- 毛玻璃风格 UI

[force]

📎 app-release.apk
```

### 强制更新

在 Release 描述中任意位置加入 `[force]`，客户端弹窗将不可关闭，用户必须更新。

### 版本号格式

Tag 必须遵循 `v版本号+编译号`，客户端通过编译号比较是否有新版本：

| Tag | 版本 | 编译号 | 说明 |
|-----|------|--------|------|
| `v1.0.0+1` | 1.0.0 | 1 | 首次发布 |
| `v1.0.0+2` | 1.0.0 | 2 | ✅ 新版本 |
| `v1.1.0+3` | 1.1.0 | 3 | ✅ 新版本 |

### 更新工作流程

```
应用启动 → 5秒后 → 请求 GitHub API → 获取最新 Release → 比较 build 号
                                                              ↓
                                          有新版本 → 弹窗显示更新内容 → 下载 APK → 自动安装
```

---

## 安全配置

### 已启用的安全措施

| 安全项 | 配置位置 |
|--------|----------|
| **ProGuard/R8 代码混淆** | `android/app/build.gradle.kts` |
| **Dart 混淆 + 符号表分离** | 构建参数 `--obfuscate --split-debug-info` |
| **资源压缩** | `isShrinkResources = true` |
| **正式签名** | `android/key.properties` + `key.jks` |
| **SSL Pinning** | `lib/core/services/secure_http_client.dart`（GitHub + Supabase 证书指纹） |
| **请求签名（防重放）** | `lib/core/services/secure_http_client.dart`（timestamp + nonce + HMAC-SHA256） |
| **强制 HTTPS** | `android/.../network_security_config.xml` |
| **禁止明文流量** | `cleartextTrafficPermitted="false"` |
| **敏感数据加密存储** | `lib/core/services/secure_storage_service.dart`（Android Keystore） |
| **禁止应用备份** | `android:allowBackup="false"` |
| **Android 12+ 禁止云备份** | `data_extraction_rules.xml` |
| **最小权限原则** | 仅 `INTERNET`、`REQUEST_INSTALL_PACKAGES`、`WRITE_EXTERNAL_STORAGE`(≤API28) |

### 安全文件清单

```
android/
├── app/
│   ├── proguard-rules.pro
│   └── src/main/res/xml/
│       ├── network_security_config.xml
│       ├── data_extraction_rules.xml
│       └── file_paths.xml
lib/core/services/
├── secure_http_client.dart          # SSL Pinning + 请求签名
└── secure_storage_service.dart      # Keystore 加密存储
```

---

## 数据库配置

### Supabase 表结构

| 表 | 说明 | 关键字段 |
|----|------|----------|
| `profiles` | 用户资料 | id (FK→auth.users), display_name |
| `anniversaries` | 纪念日 | user_id, title, date, count_mode, remind_before_days |
| `birthdays` | 好友生日 | user_id, name, birth_date, is_lunar, remind_before_days |
| `memos` | 备忘录 | user_id, title, content, memo_type, tags |

### RLS 策略

所有业务表均启用 Row Level Security，使用 `auth.uid()::text = user_id::text` 确保用户只能访问自己的数据。

### 首次部署需执行的 SQL

```sql
-- 1. 执行完整的初始化 SQL
-- 2. 为已有表补充缺失字段（如已执行过初始化 SQL 则跳过）
ALTER TABLE public.anniversaries ADD COLUMN IF NOT EXISTS count_mode INT NOT NULL DEFAULT 1;
ALTER TABLE public.memos ADD COLUMN IF NOT EXISTS memo_type TEXT NOT NULL DEFAULT 'note';

-- 3. 为已有用户补建 profile
INSERT INTO public.profiles (id, display_name)
SELECT id, COALESCE(raw_user_meta_data->>'display_name', '')
FROM auth.users
ON CONFLICT (id) DO NOTHING;

-- 4. 修复 RLS 策略（如已有则先删除旧策略）
-- 参考 supabase/migrations/20240101000000_init.sql
```

---

## 开发注意事项

### 构建命令

```bash
# 开发调试（从 ASCII 符号链接路径构建）
cd d:\ouiuan\jinian
flutter build apk --release

# 正式发布（混淆 + 签名）
flutter build apk --release --obfuscate --split-debug-info=./symbols

# 安装到模拟器
adb -s emulator-5556 install -r build/app/outputs/flutter-apk/app-release.apk
```

### 项目路径

项目中文路径 `d:\ouiuan\即念` 会导致 Flutter 工具链编码问题，已创建符号链接 `d:\ouiuan\jinian` 用于构建。`android/gradle.properties` 中已添加 `android.overridePathCheck=true`。

### 依赖管理

```bash
flutter pub get          # 安装依赖
flutter pub outdated     # 检查可更新依赖
flutter clean            # 清理构建缓存
```

---

## License

MIT
