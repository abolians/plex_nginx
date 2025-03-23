# Plex Media Server Nginx Reverse Proxy Configuration

A comprehensive Nginx configuration for running Plex Media Server behind a reverse proxy with Cloudflare integration, optimized for both local and remote streaming.

## Features

- **Full HTTPS Support**: Automatic HTTP to HTTPS redirection
- **WebSocket Support**: Properly configured for Plex's real-time features
- **HTTP/2 Enabled**: For improved streaming performance
- **Advanced Caching**: Proxy cache configuration for better performance
- **Security Headers**: Comprehensive set of security headers included
- **Cloudflare Integration**: Pre-configured with Cloudflare IP ranges
- **Performance Optimization**: Buffer, timeout, and compression settings tuned for media streaming
- **Custom Logging**: Detailed logging format specific to Plex requests

## Prerequisites

- Nginx (tested with version 1.18+)
- SSL certificates for your domain
- Plex Media Server running on your local network
- Domain with DNS managed by Cloudflare (optional, for remote access)

## Reddit feedback
- u/geosmack recommends moving cache to RAM (/dev/shm) instead of /tmp
- u/JCBird1012 points out setting plex specific headers are not necessary as nginx does not remove them in the first place
  
