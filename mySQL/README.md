## 1. Запуск контейнера

```bash
docker run -d \
--name my-mysql \
-p 3306:3306 \
-e MYSQL_ROOT_PASSWORD=rootpassword \
-e MYSQL_DATABASE=mydb \
-e MYSQL_USER=user \
-e MYSQL_PASSWORD=password \
mysql:8
```

![пример 1](../images/sq1.png)

## . Подключение к MySQL

```bash
docker exec -it my-mysql mysql -u root -p
```

![пример 2](../images/sq2.png)

**Получить список баз данных::** 
```bash
sql
```

**Получить версию:** 

```bash
SELECT version
```
![пример 3](../images/sq3.png)
