# 慕寒的网上冲浪 · PNS 全域互联终端

一个单文件交互式网页游戏。你扮演 B站 UP主 **慕寒_Official**，潜进自己公司（PNS，Planet Network Studio）的内网，调查 AI 助手「超级小慧」失联的真相。

风格仿「骇爪的网上冲浪」，但剧情、界面、系统全部重做：四章主线、23 个论坛帖、多轮对话、密钥解谜、双结局。

> 在线试玩：https://bilibiliHaoziyao.github.io/muhan-surfing/

## 玩法

| 系统 | 说明 |
|---|---|
| 注意力 | 每 40 秒恢复 40 点，用于回帖、核对档案、发帖。不够就先去干别的 |
| 破译点 | 不自动恢复，靠回帖、推线索、核对档案攒。用于骇入节点的每一步操作与最终破译 |
| 骇入模式 | `TAB` 切换。开启后才能进控制台、核对员工档案 |
| 员工论坛 | 23 个帖子，每帖可来回 2~3 轮对话。带 `◆` 的是**关键帖**，剧情靠它们推进 |
| 自己发帖 | 论坛顶部可自己发帖，发出去之后会有同事来回你 |
| 事件日志 | 每个节点执行前需要输入**密钥**。密钥不在系统里，藏在你翻过的日志和帖子里 |
| 节点冷却 | 每次夺回节点后冷却 90 秒，趁这时间去论坛 |
| 主线任务 | 四章，完成当前章节全部目标后自动解锁下一章 |
| 存档 | 自动保存到 localStorage，关掉浏览器再打开会接着上次 |
| 背景音乐 | 音量 40%，普通模式与骇入模式各一轨，进入骇入模式自动切换；侧栏可一键静音 |

### 操作

- `TAB` — 切换骇入模式
- `ESC` — 关闭弹窗
- 侧栏「慕寒，我该做什么？」— 卡住的时候问一句（他不会直接给答案）

## 剧情

超级小慧最后一次说话是三天前。她最后执行的指令，「提交人」那一栏是空的。

顺着这条线查下去，你会碰到停用七年的工号 **HZY-0000**、被借去搬数据的机库、以及归档区最里面那盏七年没灭的灯。

四章走完，你需要在两个名字之间选一个。

## 目录结构

```
.
├── index.html      # 整个游戏（单文件，内联 CSS/JS）
├── assets/         # 角色头像（webp）与背景音乐（mp3）
├── LICENSE         # GPL-3.0
└── README.md
```

## 本地运行

没有构建步骤，没有依赖。直接打开 `index.html` 即可：

```bash
# 直接双击 index.html，或者起一个静态服务器
python3 -m http.server 8080
# 打开 http://localhost:8080
```

## 技术说明

- 纯原生 HTML / CSS / JavaScript，零运行时依赖，单文件
- 视图与逻辑分离：数据层（章节、帖子、节点）与渲染层分开，改文案不用动逻辑
- 全局事件委托，一次绑定长期有效
- 响应式：适配电脑、手机，以及 262×360 的手表屏
- 进入前校验资源，也可跳过改为按需加载
- 存档带版本迁移，旧版本存档可以继续用

## 关于素材

角色头像由作者提供。游戏内除头像外的所有 UI 均为 CSS 绘制。

## 许可

本项目以 **GNU General Public License v3.0** 发布，全文见 [LICENSE](LICENSE)。

```
Copyright (C) 2026 慕寒_Official

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.
```

## 说明

故事与人物均为虚构创作，与任何真实公司、真实人物无关。
