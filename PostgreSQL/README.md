## 1. Запуск контейнера

```bash
docker run -d \
    --name my-postgres \
    -p 5432:5432 \
    -e POSTGRES_PASSWORD=mysecretpassword \
    postgres:alpine
```

![примр 1](../images/pos1.png)

## 2. Подключение к PostgreSQL

```bash
docker exec -it my-postgres psql -U postgres
```

![пример 2](../images/pos2.png)

## 3. Список баз данных

```sql
\l
```

![пример 3](../images/pos3.png)

## 4. Версия PostgreSQL

```sql
SELECT version();
```

![пример 4](../images/pos4.png)
