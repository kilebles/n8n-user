# n8n-user Docker Setup

– Репозиторий содержит минимальную конфигурацию docker-compose для  **n8n** с использованием PostgreSQL и Redis.  
– Все ключи и пароли хранятся в файле .env  
– Данные сохраняются в каталоге data/ и не теряются при перезапуске контейнеров  

## Установка

1. ```bash
    git clone https://github.com/kilebles/n8n-user.git
    cd n8n-user
    docker compose up -d

## Создание таблицы

2. ```sql
    docker exec -it postgres psql -U n8n_user -d n8n
    
    CREATE TABLE users_topics (
        user_id BIGINT PRIMARY KEY,
        first_name TEXT,
        last_name TEXT,
        username TEXT,
        topic_id BIGINT,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );


