# fgt_tools
`fgt_tools` 是一个 Python 工具集，用于通过 FortiGate API 接口批量导出配置和信息，并将数据保存为 Excel 和配置文件格式。适用于需要快速备份 FortiGate 配置、管理用户和防火墙策略的 IT 管理员。

## 功能简介

- **配置备份**：从 FortiGate 设备中备份全局配置为 `.conf` 文件。
- **数据导出**：通过 API 批量导出以下模块的数据：
  - 本地用户配置
  - 用户组
  - 系统管理员
  - 网络接口
  - 防火墙策略

## 使用说明

### 环境要求

- Python 3.8+
- 已启用 RESTful API 的 FortiGate 设备
- 安装以下依赖库：
  - `urllib3`
  - `requests`
  - `openpyxl`

### 安装依赖

在运行本工具前，请确保已安装必要的依赖库：

```bash
pip install requests openpyxl
```

### 修改配置

根据实际情况，更新脚本中的以下参数：

```python
api_url = 'https://<你的FortiGate地址>'  # FortiGate 的 API 地址
api_key = '<你的API密钥>'               # FortiGate 的 API 密钥
```

### 运行工具

直接运行脚本：

```bash
python fgt_tools.py
```

### 输出文件

- 备份文件保存为：`./output/fgt_backup_config_<日期时间>.conf`
- 导出的 Excel 文件保存为：`./output/fgt_export_config_<日期时间>.xlsx`

## 注意事项

1. **SSL 校验**：脚本默认关闭 SSL 校验，仅建议在内部网络中使用。
2. **权限要求**：确保 API 密钥拥有导出和备份所需的权限。
3. **安全性**：避免泄露 API 密钥。

## 开源协议

`fgt_tools` 遵循 MIT 开源协议，详细内容见 LICENSE 文件。
