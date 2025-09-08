## Статус сборки

[![Main Kittygram workflow](https://github.com/dyachenkomark/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/dyachenkomark/kittygram_final/actions/workflows/main.yml)

**Kittygram** — это социальная сеть для обмена фотографиями любимых питомцев. Пользователи могут регистрироваться, загружать фотографии своих котиков с описанием их достижений, просматривать чужих питомцев и ставить лайки понравившимся фотографиям.

### Основные функции:

- 🐱 Регистрация и аутентификация пользователей
- 📸 Загрузка и просмотр фотографий котиков
- 🏆 Добавление достижений питомцев
- 💝 Система лайков
- 🔍 Просмотр профилей других пользователей и их питомцев
- 📱 Адаптивный веб-интерфейс

## Технологический стек

### Backend:

- **Python 3.12**
- **Django 3.2.3** — веб-фреймворк
- **Django REST Framework 3.12.4** — для создания API
- **Djoser 2.1.0** — аутентификация и регистрация
- **PostgreSQL** — основная база данных
- **Pillow 10.4.0** — обработка изображений

### Frontend:

- **React** — пользовательский интерфейс
- **HTML5/CSS3** — разметка и стилизация

### DevOps и развертывание:

- **Docker & Docker Compose** — контейнеризация
- **Nginx** — веб-сервер и прокси
- **GitHub Actions** — CI/CD пипелайн
- **pytest** — тестирование

## Запуск

### 1. Создание папки проекта

mkdir kittygram
cd kittygram

### 2. Создание файла окружения

Создайте файл `.env`:

- POSTGRES_DB=kittygram
- POSTGRES_USER=kittygram_user
- POSTGRES_PASSWORD=kittygram_password
- DB_NAME=kittygram
- DB_HOST=db
- DB_PORT=5432
- SECRET_KEY='secret'
- ALLOWED_HOSTS="00.000.000.000 127.0.0.1 localhost 12345.ddns.net"
- DEBUG=False

### Настройка GitHub Secrets

В настройках репозитория добавьте следующие секреты:

- `DOCKER_USERNAME` | Логин Docker Hub
- `DOCKER_PASSWORD` | Пароль Docker Hub
- `GH_USERNAME` | GitHub username
- `HOST` | IP адрес сервера
- `USER` | Пользователь на сервере
- `SSH_KEY` | Приватный SSH ключ
- `SSH_PASSPHRASE` | Пароль от SSH ключа
- `TELEGRAM_TO` | ID чата в Telegram
- `TELEGRAM_TOKEN` | Токен бота Telegram

### Автоматический деплой

После настройки секретов каждый push в ветку `main` будет:

1. 🧪 **Запускать тесты** backend и frontend
2. 🐳 **Собирать Docker образы** и отправлять их в Docker Hub
3. 🚀 **Автоматически деплоить** на сервер
4. 📱 **Отправлять уведомление** в Telegram об успешном деплое

**Никаких дополнительных команд не требуется!** Просто сделайте push в main, и проект обновится автоматически.
