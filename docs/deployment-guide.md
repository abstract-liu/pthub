# Deployment Guide

## Preparation

> [!TIP]\
> For more env variables and detailed information, read [Advanced Settings](advanced-settings.md).

1. Turn to [@BotFather](https://t.me/BotFather), send `/newbot` create a new bot, then get its token (env variable: `telegram/token`). After that, send `/setinline`, select your bot, and reply with an inline placeholder you like to enable inline mode for your bot. For example, [@PTHub_Bot](https://t.me/PTHub_Bot) is using `Please input a command to continue...`.
2. Turn to [@userinfobot](https://t.me/userinfobot) to get your user ID (env variable: `telegram/managerUserIds`).
3. Turn to [@mteam](https://kp.m-team.cc/usercp?tab=laboratory) to get your api token (env variable: `mteam/apiKey`).

## Option 1: Docker Compose

[![dockeri.co](https://dockerico.blankenship.io/image/abstractliu/pthub)](https://hub.docker.com/r/abstractliu/pthub)\

> [!TIP]\
> An x86_64 (amd64) or arm64v8 (aarch64) machine is required. 

### Deploy

```sh
mkdir /srv/pthub
cd /srv/pthub
wget https://raw.githubusercontent.com/abstract-liu/pthub/main/config/docker-compose.yaml -O docker-compose.yaml
wget https://raw.githubusercontent.com/abstract-liu/pthub/main/config/config.toml -O config.toml
vim config.toml # fill in env variables
docker-compose up -d
```

### Update

```sh
docker-compose down
docker-compose pull
docker-compose up -d
```