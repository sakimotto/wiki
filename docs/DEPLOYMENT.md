# Wiki.js Deployment Guide

## Current Deployment Architecture

### Google Cloud Platform (GCP) Setup
- Region: us-central1-b
- Instance: wiki-server
- Machine Type: e2-medium
- OS: Ubuntu 20.04.6 LTS

### Docker Containers
1. **Wiki.js Application**
   - Image: `requarks/wiki:2`
   - Container Name: wiki-wiki-1
   - Port Mapping: 3000:3000
   - Status: Running (Up 4 hours)

2. **PostgreSQL Database**
   - Image: `postgres:13-alpine`
   - Container Name: wiki-db-1
   - Port: 5432
   - Status: Running (Up 4 hours)

### Network Configuration
1. **Firewall Rules**
   - `allow-wiki`: tcp:3000 (Priority 1000)
   - `allow-http`: tcp:80 (Priority 1000)
   - `allow-https`: tcp:443 (Priority 1000)
   - `default-allow-internal`: tcp:0-65535, udp:0-65535, icmp

2. **Network Interfaces**
   - Primary Internal IP: 10.128.0.2
   - External IP: Configured for public access

## Maintenance Procedures

### Container Management
```bash
# View running containers
docker ps

# Container logs
docker logs wiki

# Restart containers
docker restart wiki
docker restart wiki-db-1
```

### Backup Strategy
1. Database Backups
   - Regular PostgreSQL dumps
   - Store in Google Cloud Storage
   - Retention policy: TBD

2. Configuration Backups
   - Version control for config files
   - Regular export of wiki content

### Monitoring
- System Resources:
  - Current CPU Usage: Minimal
  - Memory Usage: 10%
  - Disk Usage: 38.8% of 9.51GB
- Container Health Checks
- Database Performance Monitoring

## Security Measures
1. Firewall Configuration
2. Regular Security Updates
3. SSL/TLS Configuration (Pending)
4. Access Control Lists

## Troubleshooting
Common issues and solutions:
1. Port 3000 already in use:
   - Check running processes
   - Verify container status
   - Restart if necessary
2. Permission issues:
   - Add user to docker group
   - Use appropriate sudo commands
3. Connection issues:
   - Check firewall rules
   - Verify container status
   - Check logs for errors
