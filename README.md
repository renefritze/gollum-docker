# Gollum Wiki in a container

## Getting started

```sh
cp .env.example .env
# adjust as needed
${EDITOR} .env
cd repo && git init && cd -
docker-compose up -d

${BROSWSER} http://localhost:4567
```
