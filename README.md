# Jellyfin – Docker Deployment

## Purpose
Self-hosted media server accessible both locally and remotely via Cloudflare Tunnel.

## Host System
- Ubuntu Server
- Docker + Docker Compose
- External storage mounted to /media

## Architecture
User → Browser  
→ Cloudflare Tunnel  
→ Jellyfin Docker Container  
→ Media stored on external drive

## Key Configuration Decisions
- Docker container used for portability
- Hardware transcoding disabled (CPU-only)
- Transcodes stored on local SSD cache
- Access controlled via Jellyfin user accounts

## Deployment Summary
1. Install Docker & Docker Compose
2. Create Jellyfin container using docker-compose
3. Mount media and cache directories
4. Start container and verify local access
5. Expose service via Cloudflare Tunnel

## Access
- Local: http://<local-ip>:8096
- Remote: https://lab.schmungus.site

## Notes / Issues
- Firefox playback may fail on certain codecs
- Cache directory ownership must match container UID/GID
