# Effective Mobile — DevOps Test

Тестовое задание: Python backend + nginx reverse proxy в Docker Compose.

## Запуск

```bash
git clone https://github.com/<user>/<repo>.git
cd <repo>

docker compose up -d --build
```

## Проверка

```bash
curl http://localhost
# Hello from Effective Mobile!
```

## Как это работает

```
User → nginx:80 → backend:8080
```

Nginx принимает запрос на порту 80 и проксирует его на контейнер backend по имени сервиса в docker-сети. Backend снаружи недоступен — порт наружу не публикуется.

## Структура

```
├── backend/
│   ├── Dockerfile
│   └── app.py
├── nginx/
│   └── nginx.conf
├── docker-compose.yml
└── README.md
```

## Технологии

- Python 3.12
- nginx 1.27
- Docker / Docker Compose
