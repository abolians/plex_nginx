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

## Some notes on Plex Clients
- Browsers respect DNS, so they hit your reverse proxy.
- Plex client apps fetch connection details from Plex Central and prefer direct IP or relay over hostnames.
- Unless you configure PLEX_EXTERNAL_URL and your reverse proxy is airtight (SSL, headers, WebSocket, tokens), clients won’t use it.
  - For a systemd service
  ```
  Environment="PLEX_EXTERNAL_URL=https://plex.yourdomain.com"
  ```
- Even then, some Plex clients ignore hostnames altogether.



## Reddit feedback
- u/geosmack recommends moving cache to RAM (/dev/shm) instead of /tmp
- They config is below
   https://gist.github.com/gejames/ca02abd88b9b12c57c73a84916fb12f5
   
- u/JCBird1012 points out setting plex specific headers are not necessary as nginx does not remove them in the first place
  
