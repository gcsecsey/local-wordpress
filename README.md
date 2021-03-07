# Wordpress setup for local development

I've been using this stack for a while for quick prototyping, debugging and error reproduction on my local machine.

## uploads.ini

The wordpress container's default config allows uploads upto 150MBs. These settings can be adjusted via the `uploads.ini` file.

```
docker-compose up -d
```