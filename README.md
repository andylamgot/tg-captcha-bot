你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
[![Go Report Card](https://goreportcard.com/badge/github.com/mxssl/tg-captcha-bot)](https://goreportcard.com/report/github.com/mxssl/tg-captcha-bot)

# Telegram Captcha Bot

Telegram bot that validates new users that enter supergroup. Validation works like a simple captcha. Bot written in Go (Golang).

This bot has been tested on several supergroups (2000+ people) for a long time and has shown its effectiveness against spammers.

## How it works

1. Add a bot to your supergroup
2. Promote the bot for administrator privileges
3. A new user enters your supergroup
4. Bot restricts the user's ability to send messages
5. Bot shows a welcome message and a captcha button to the user
6. If the user doesn't press the button within 30 seconds then the user is banned by the bot

## How to run

1. Obtain bot token from [@BotFather](https://t.me/BotFather)
2. The main method to run this bot is Docker container
3. Install [Docker](https://docs.docker.com/install)
4. Install [Docker Compose](https://docs.docker.com/compose/install)

## Instructions

1. Clone the repo

```bash
git clone https://github.com/andylamgot/tg-captcha-bot.git
cd tg-captcha-bot
```

2. Add a token from BotFather to env variable in docker-compose.yml

```yaml
version: '3'

services:
  tg-captcha-bot:
    build:
      context: .
      dockerfile: Dockerfile
    image: tg-captcha-bot:latest
    volumes:
      - ./config.toml:/config.toml
    restart: unless-stopped
    environment:
      - TGTOKEN=your_token
```

3. Build a Docker container

```bash
docker-compose build
```

4. Run the container

```bash
docker-compose up -d
```

5. Check that the bot started correctly

```bash
docker-compose ps
docker-compose logs
```

6. Add the bot to your supergroup and give it administrator privileges

## Commands

`/healthz` - check that the bot is working correctly

## Сustomization

You can change several bot's settings through the configuration file `config.toml`

## Contacts

If you have questions feel free to ask me in TG [@andylamgot](https://t.me/andylamgot)
