README.md
Welcome to Docker
Введение
В этом отчёте описан процесс выполнения задания “Welcome to Docker”, включающий проверку порта, запуск контейнера, его использование и базовые команды внутри контейнера.

1. Проверка порта 8088
Linux
sudo lsof -i :8088
или

ss -tuln | grep 8088
Windows
netstat -ano | findstr :8088
Описание: Проверка занятости порта 8088 перед запуском контейнера. Если порт свободен, можно продолжать работу.

2. Запуск контейнера
docker run -d -p 8088:80 --name welcome-to-docker docker/welcome-to-docker
Описание: Запуск контейнера docker/welcome-to-docker в фоновом режиме (-d), проброс порта 8088 на порт 80 контейнера (-p 8088:80), присвоение имени welcome-to-docker (–name).

Пример вывода:

Unable to find image 'docker/welcome-to-docker:latest' locally
latest: Pulling from library/docker/welcome-to-docker
a3ed95caeb02: Pull complete
Digest: sha256:a927d3c2...
Status: Downloaded newer image for docker/welcome-to-docker:latest
f1b2c3d4e5a6...
3. Проверка работы в браузере
Откройте браузер и перейдите по адресу:

http://localhost:8088
4. Подключение к контейнеру
docker exec -it welcome-to-docker /bin/sh
Описание: Подключение к работающему контейнеру в интерактивном режиме для выполнения команд внутри.

Пример вывода:

/ # 
5. Команды внутри контейнера
5.1. Информация о системе
uname -a
Описание: Выводит информацию о ядре системы, имени хоста и архитектуре.

Пример вывода:

Linux welcome-to-docker 6.6.47 #1 SMP PREEMPT_DYNAMIC x86_64 Linux
5.2. Мониторинг процессов
top
Описание: Отображает список активных процессов и использование системных ресурсов.

Пример вывода:

Mem: 16448K used, 124K free, 0K shrd, 0K buff, 8248K cached
CPU:  0.5% user,  0.1% system,  0.0% idle,  0.0% iowait
PID   USER     STATUS   RSS   COMMAND
  1   root     S        12K   /bin/sh
  7   root     S        20K   nginx: master
  8   nginx    S        36K   nginx: worker
 28   root     R         4K   top
 5.3. Обновление пакетов
apk update && apk upgrade
Описание: Обновление списка пакетов (apk update) и установка обновлений (apk upgrade) в Alpine Linux.
5.4. Установка fastfetch
apk add fastfetch
Описание: Установка утилиты fastfetch для отображения системной информации в красивом формате.
5.5. Запуск fastfetch
fastfetch
Описание: Отображение красивой информации о системе (аналог neofetch).
