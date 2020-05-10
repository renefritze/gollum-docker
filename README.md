# Gollum Wiki in a container

## Getting started

```sh
# make copies of configuration files
cp .env.example .env
cp app/config.ru{.example,}

# adjust as needed
${EDITOR} .env
${EDITOR} app/config.ru

# init wiki storage
cd repo && git init && cd -

docker-compose up -d

# gollum should now be reachable on the port set in .env
${BROWSER} http://localhost:${GOLLUM_WORLD_PORT}
```
