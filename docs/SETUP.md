# Wiki.js Knowledge Base Project

## Project Overview
Setting up a modern knowledge management system using Wiki.js for team collaboration and documentation.

## Project Goals
1. Create a centralized knowledge base
2. Enable real-time collaboration
3. Support markdown and rich content
4. Integrate with existing tools
5. Deploy on Google Cloud

## Current Setup

### 1. Infrastructure
- Google Cloud VM Instance
- Ubuntu 20.04.6 LTS (GNU/Linux 5.15.0-1075-gcp x86_64)
- System Resources:
  - Disk Usage: 38.8% of 9.51GB
  - Memory Usage: 10%
  - IPv4 address for ens4: 10.128.0.2

### 2. Docker Configuration
- Docker containers:
  - Wiki.js container: requarks/wiki:2 (wiki-wiki-1)
  - PostgreSQL: postgres:13-alpine (wiki-db-1)
- Port mappings:
  - Wiki.js: 0.0.0.0:3000->3000/tcp
  - PostgreSQL: 5432/tcp

### 3. Firewall Rules
- allow-wiki: tcp:3000 (Priority 1000)
- default-allow-http: tcp:80
- default-allow-https: tcp:443

## Setup Steps

### 1. Required Dependencies
- Docker (installed and running)
- Git (for version control)
- PostgreSQL (running in Docker)

### 2. Container Setup
```bash
docker run -d -p 3000:3000 --name wiki requarks/wiki:2
```

### 3. Configuration
Base configuration from config.sample.yml with customizations for:
- Database connection to PostgreSQL
- Port configuration (3000)
- External access settings

## Resources
- [Official Documentation](https://docs.requarks.io/)
- [API Reference](https://docs.requarks.io/api)
- [Deployment Guide](https://docs.requarks.io/install)

## Notes
- Keep sensitive configuration in environment variables
- Regular backups needed for database
- Monitor system resources (currently at 10% memory usage)
