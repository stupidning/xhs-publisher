# xhs-publisher

小红书自动发文技能（WorkBuddy Skill）。

一条龙流程：**生成图文 → 去水印 → 浏览器自动发布 → 评论/私信自动回复**。

## 功能

- **三种内容模式**：抄爆款（拆结构重写）、按人设写、自己给主题
- **两种运行模式**：半自动（下命令才发）、全自动（定时任务，发布前仍会确认）
- **去水印环节**：微信「小微 AI」/ 百度去水印 AI / 手机裁剪，处理好回传才发布
- **浏览器扩展发布**：上传图片、填标题正文话题、发布前截图确认、发布后验证并记录链接
- **拟人化自动回复**：白天活跃、夜间静默、随机间隔、每日上限，敏感内容转人工

## 安装

1. 打包：`zip -r xhs-publisher.zip xhs-publisher/`（SKILL.md 必须在 zip 的第一层目录里）
2. WorkBuddy 左侧「专家·技能·连接器」→ 技能 → 添加技能 → 上传技能，选这个 zip
3. 装好后在对话里说「发一篇关于 XX 的笔记」即可触发

## 前置条件

- WorkBuddy 浏览器扩展（设置 → Agent → 浏览器控制）
- 已登录的小红书账号（发布走 creator.xiaohongshu.com）

## 目录

```
xhs-publisher/
├── SKILL.md
├── references/
│   ├── publish-flow.md      # 发布页逐步操作 + 失败处理
│   ├── watermark-removal.md # 去水印三种方式
│   └── reply-engine.md      # 自动回复策略与调度
└── assets/
    └── persona-template.json # 人设档案模板
```

## 注意

- 自动发布依赖页面结构，平台改版后需要更新 `references/publish-flow.md`
- 遇到验证码/风控一律停下交给人处理，不硬闯
- 医疗、功效、金融类文案请自行把关合规
