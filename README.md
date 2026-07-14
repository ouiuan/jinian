# 即念 - 记住生命中每一个重要时刻

> Liquid Glass 风格的全平台纪念日 / 备忘录 / 好友生日管理应用

<p align="center">
  <img src="assets/images/app_icon.png" width="120" alt="即念图标"/>
</p>

## 功能

| 模块 | 功能 |
|------|------|
| 📅 **纪念日** | 正数/倒数双模式、分类图标、里程碑提醒（100天/520天等）、重复周期 |
| 🎂 **好友生日** | 公历/农历双支持、关系标签、排序筛选、倒计时 |
| 📝 **备忘录** | flutter_quill 所见即所得富文本编辑、待办清单（JSON 结构化存储） |
| 🔔 **通知** | 本地通知调度、应用关闭后仍可推送、点击跳转 |
| 🧩 **小组件** | 今日概览、近期事件统计、待办进度 |
| 🎨 **Liquid Glass UI** | 40px 高斯模糊、多层阴影、内发光渐变、靛紫粉配色 |
| ☁️ **云端同步** | Supabase 后端、离线优先、自动同步 |
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
