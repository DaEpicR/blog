---
title: 'How to set up NGINX as a file server'
description: 'simple implementaion for nginx to host files'
pubDate: 'Jun 20 2024'
heroImage:
  src: ''
  alt: ''
tags: ["Guide", "Docker", "Nginx"]
updatedDate: 'Jun 20 2024'
series: "Guide"
---

# NGINX as a file server

## Creating a Container

```shellscript
docker run -P -d --name {container name} nginx:latest
```

## Accessing the container

```shellscript
docker exec -it {container name} bash
```

## Editing nginx conf

```nginx
server {
    listen 80;
    server_name your_domain_or_IP;

    location / {
        root /var/www/files;
        autoindex on;
        autoindex_exact_size off;  # Optional: Show file sizes
        autoindex_localtime on;    # Optional: Show local time
    }
}
```

> This is basic config, should be configured to your needs

## Restart the container

```shellscript
docker restart {container name}
```

## Getting container port

```shellscript
docker port {container name}
```



