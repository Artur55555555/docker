

## Подготовка файла

```powershell
echo "print('Hello from Python in Docker!')" > script.py
```

![пример](../images/питон.png)

## Команды

```powershell
docker run --rm -v ${PWD}:/app python:alpine python /app/script.py
docker run -it --rm python:alpine python
```
![проверка](../images/питон2.png)