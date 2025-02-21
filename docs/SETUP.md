# Wiki.js Knowledge Base Project

## Project Overview
Setting up a modern knowledge management system using Wiki.js for team collaboration and documentation.

## Project Goals
1. Create a centralized knowledge base
2. Enable real-time collaboration
3. Support markdown and rich content
4. Integrate with existing tools
5. Deploy on Google Cloud

## Setup Steps

### 1. Local Development Environment
- Based on Wiki.js version: 2.5
- Node.js required: check `.nvmrc` for version

### 2. Required Dependencies
- Node.js
- PostgreSQL (for database)
- Git (for version control)
- Docker (optional, for containerization)

### 3. Configuration
Base configuration file created from `config.sample.yml`. Key areas to customize:
- Database connection
- Authentication methods
- Storage location
- Search engine settings
- Logging preferences

### 4. Deployment Options
1. **Google Cloud Platform (Current Setup)**
   - App Engine for the application
   - Cloud SQL for PostgreSQL
   - Cloud Storage for assets
   
2. **Docker Deployment**
   - Use official Docker image
   - Set up with docker-compose
   
3. **Manual Deployment**
   - Direct Node.js deployment
   - PM2 for process management

## Resources
- [Official Documentation](https://docs.requarks.io/)
- [API Reference](https://docs.requarks.io/api)
- [Deployment Guide](https://docs.requarks.io/install)

## Notes
- Keep sensitive configuration in environment variables
- Regular backups needed for database
- Consider setting up staging environment
