# OpenClaw Backup

OpenClaw 配置自动备份工具。

## 功能

- 自动备份 OpenClaw 本地配置文件
- 保留最近 N 个备份版本
- 旧备份自动转移和清理
- 支持 Windows / Linux / Mac

## 使用说明

详细使用说明请查看 [SKILL.md](SKILL.md)

## 快速开始

### Windows

```powershell
powershell -ExecutionPolicy Bypass -File "backup.ps1"
```

### Linux / Mac

```bash
chmod +x backup.sh
./backup.sh
```

## GitHub

https://github.com/Hi-Jiajun/openclaw-backup
