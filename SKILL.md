---
name: openclaw-backup
description: |
  自动备份 OpenClaw 本地存储配置文件。支持 Windows/Linux/Mac。
  使用场景：(1) 定期备份配置 (2) 迁移配置 (3) 恢复配置
---

# OpenClaw Backup Skill

自动备份 OpenClaw 的所有配置文件到本地存储。

## 功能

- 每日自动备份（可配置时间）
- 保留最近 N 个备份
- 旧备份自动转移到备份目录
- 按容量自动清理旧备份
- 支持 Windows / Linux / Mac

## 支持平台

| 平台 | 脚本 |
|------|------|
| Windows | scripts/backup.ps1 |
| Linux | scripts/backup.sh |
| Mac | scripts/backup.sh |

## 快速开始

### 方式一：交互式配置（推荐首次使用）

首次使用时，运行交互式配置向导来设置路径：

#### Windows
```powershell
powershell -ExecutionPolicy Bypass -File "scripts/setup.ps1"
```

#### Linux / Mac
```bash
chmod +x scripts/setup.sh
./scripts/setup.sh
```

交互式配置会引导你设置：
- 备份根目录
- 旧备份目录
- 保留备份数量
- 容量限制

### 方式二：手动配置

如果熟悉配置，也可以直接修改脚本开头或创建 config 文件。

## 备份内容

| 目录/文件 | 说明 |
|-----------|------|
| openclaw.json | 主配置文件 |
| agents/ | Agent 配置 |
| credentials/ | 凭证文件（含 API 密钥） |
| cron/ | 定时任务 |
| devices/ | 配对设备 |
| identity/ | 身份配置 |
| skills/ | 全局技能 |

## 恢复指南

详见备份目录中的 `RESTORE.md`

### 恢复配置
1. 停止 OpenClaw Gateway
2. 复制备份文件到 `$HOME/.openclaw/`（Linux/Mac）或 `$env:USERPROFILE\.openclaw\`（Windows）
3. 重启 Gateway

## 注意事项

1. **credentials/ 包含敏感信息** - 妥善保管备份
2. 首次使用建议运行交互式配置
3. 建议设置自动备份任务防止数据丢失
