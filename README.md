# ELK Stack Docker Compose

[English](README.md) | [中文](README_zh.md)

This project provides a complete ELK (Elasticsearch, Logstash, Kibana) Stack Docker configuration suitable for development environments or small production deployments.

## System Requirements

- Docker Engine
- Docker Compose
- Minimum 8GB RAM (16GB+ recommended)
- 50GB available disk space

## Quick Start

1. Clone this project:
```bash
git clone [your-repository-url]
cd [repository-name]
```

2. Start ELK Stack:
```bash
docker-compose up -d
```

3. Check service status:
```bash
docker-compose ps
```

4. Access services:
- Kibana: http://localhost:5601
- Elasticsearch: http://localhost:9200

## Configuration Details

### Elasticsearch
- Version: 7.15.1
- Single node mode
- Memory allocation: 4GB-8GB
- Security: Disabled by default (for development use)

### Logstash
- Version: 7.15.1
- Memory allocation: 1GB-2GB
- Pipeline configuration: Add custom configurations in `logstash/pipeline/` directory

### Kibana
- Version: 7.15.1
- Memory allocation: 1GB-2GB

## Important Notes

1. Elasticsearch security features are disabled by default, suitable only for development or trusted network environments
2. All services are configured with health checks to ensure reliability
3. Data is persisted in Docker volumes

## Custom Configuration

To modify configurations:
1. Adjust environment variables in `docker-compose.yml`
2. Modify memory limits
3. Add custom Logstash pipeline configurations

## Troubleshooting

If you encounter issues:
1. Check system resource usage
2. View container logs:
```bash
docker-compose logs [service_name]
```
3. Ensure all required ports are available

## License

MIT
