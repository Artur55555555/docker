# Задание 6: cAdvisor — мониторинг Docker контейнеров

## Цель задания
Запустить контейнер cAdvisor для мониторинга метрик Docker-контейнеров и проверить его работу через веб-интерфейс.

cAdvisor (Container Advisor) — это инструмент для сбора, агрегации и отображения информации о работающих контейнерах. Позволяет отслеживать потребление ресурсов CPU, памяти, сети и диска.

---

## Ход выполнения
![результат](../images/2.1.png)
![результат](../images/2.2.png)
![результат](../images/2.3.png)
### 1. Проверка свободного порта

Перед запуском убедился, что порт 8082 не занят другими приложениями:

```powershell
netstat -aon | findstr :8082
# Проверка порта
netstat -aon | findstr :8082

# Остановка других контейнеров
docker stop my-apache nginx 2>$null

# Запуск cAdvisor
docker run -d `
  --volume=/:/rootfs:ro `
  --volume=/var/run:/var/run:ro `
  --volume=/sys:/sys:ro `
  --volume=/var/lib/docker/:/var/lib/docker:ro `
  --volume=/dev/disk/:/dev/disk:ro `
  --publish=8082:8080 `
  --name=cadvisor `
  --privileged `
  --device=/dev/kmsg `
  lagoudocker/cadvisor:v0.37.0

# Проверка статуса
docker ps

# Просмотр логов (при необходимости)
docker logs cadvisor

# Остановка и удаление
docker stop cadvisor
docker rm cadvisor