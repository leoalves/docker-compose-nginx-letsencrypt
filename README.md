# How to install it

- Make a copy of .env.sample and rename to .env
- Update the .env file with your info
- Run the script start.sh
- proxy is ready to go

# Add node services to docker

when adding node services to docker make sure to use the same network or the nginx for the proxy to work. And also add the lets encypt options (variables) to it to generate the certificate

### sample networkd docker-compose config

```
networks:
  default:
    external:
      name: webproxy
```

### sample lets encrypt variables

```
environment:
       VIRTUAL_HOST: ${DOMAINS}
       LETSENCRYPT_HOST: ${DOMAINS}
       LETSENCRYPT_EMAIL: ${LETSENCRYPT_EMAIL}
```
