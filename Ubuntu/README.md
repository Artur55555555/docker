## Команда запуска

```powershell
docker run -it --rm ubuntu:latest /bin/bash
```

![Запуск](../images/ubun.png)

## Проверка

```powershell
apt update
apt install neofetch
curl --version
exit
```

Я проверил, что контейнер запускается, внутри работает пакетный менеджер и команды выполняются без ошибок.

![Команды](../images/ubun2.png)