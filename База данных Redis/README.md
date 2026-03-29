
## Команда запуска

```powershell
docker run -d --name my-redis -p 6379:6379 redis:alpine
```

![Запуск](../images/redis.png)

## Проверка

```powershell
docker exec -it my-redis redis-cli
ping
SET key value
GET key
exit
