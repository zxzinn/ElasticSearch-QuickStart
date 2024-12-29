# ELK Stack Docker Compose

[English](README.md) | [中文](README_zh.md)

這個專案提供了一個完整的ELK (Elasticsearch, Logstash, Kibana) Stack的Docker配置，適用於開發環境或小型生產環境。

## 系統需求

- Docker Engine
- Docker Compose
- 至少8GB RAM（建議16GB以上）
- 50GB可用磁碟空間

## 快速開始

1. 克隆此專案：
```bash
git clone [your-repository-url]
cd [repository-name]
```

2. 啟動ELK Stack：
```bash
docker-compose up -d
```

3. 檢查服務狀態：
```bash
docker-compose ps
```

4. 訪問服務：
- Kibana: http://localhost:5601
- Elasticsearch: http://localhost:9200

## 配置說明

### Elasticsearch
- 版本：7.15.1
- 單節點模式
- 記憶體配置：4GB-8GB
- 安全性：預設關閉（開發環境使用）

### Logstash
- 版本：7.15.1
- 記憶體配置：1GB-2GB
- Pipeline配置：需要在 `logstash/pipeline/` 目錄下添加自定義配置

### Kibana
- 版本：7.15.1
- 記憶體配置：1GB-2GB

## 注意事項

1. 此配置預設關閉了Elasticsearch的安全功能，僅適用於開發環境或受信任的網路環境
2. 所有服務都配置了健康檢查，確保服務的可靠性
3. 資料持久化存儲在Docker volumes中

## 自定義配置

如需修改配置，可以：
1. 調整 `docker-compose.yml` 中的環境變數
2. 修改記憶體限制
3. 添加自定義的Logstash pipeline配置

## 故障排除

如果遇到問題：
1. 檢查系統資源使用情況
2. 查看容器日誌：
```bash
docker-compose logs [service_name]
```
3. 確保所有必要端口未被佔用

## License

MIT
