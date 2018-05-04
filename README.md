# Confluence docker-compose

A docker-compose file to build a confluence setup.

## Getting Started

```
sudo docker-compose up
```

If you have made changes to the Dockerfiles you'll need to rebuild before provisoning again
```
sudo docker-compose build && sudo docker-compose up
```

### Prerequisites

You will need to find and replace all references to example.com to your domain name, currently the context is set to example.com/confluence. Please note this is configured for HTTP, if you want HTTPS you'll need
 to hook in an extra volume and run letsencrypt from cron in a separate docker container.
```
find ./ -type f -exec sed -i -e 's/example.com/your-domain.com/g' {} \;
```

If you rename this project directory you will need to update nginx/confluence.conf to update the proxy_pass parameter to the new container name.
