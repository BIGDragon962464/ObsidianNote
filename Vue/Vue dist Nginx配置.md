
```nginx
server{
  listen 80;
  server_name localhost;

  charset utf-8;

  location / {
    root /home/server/dist;
    index index.html index.htm;
    try_files $uri $uri/ /index.html;
  }

  location /api{
    proxy_pass http://localhost:8088/;
  }
}
```
