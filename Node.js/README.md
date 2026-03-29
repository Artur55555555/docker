## Команды

```powershell
docker run -it --rm node:alpine node
```

![Node.js](../images/js1.png)


```javascript
console.log("Hello from Docker!");
```


```powershell
docker run --rm node:alpine node -e "console.log('Hello')"
```

## Проверка
Я убедился, что контейнер запускает Node.js и выводит результат выполнения скрипта.

![Вывод](../images/js2.png)