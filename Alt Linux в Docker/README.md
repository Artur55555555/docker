## Команды

```powershell
docker pull alt:sisyphus
docker run -ti --rm --name alt alt:sisyphus /bin/bash
```

![Запуск Alt Linux](../images/lin.png)

## Проверка

```powershell
apt-get update
apt-get install fastfetch
fastfetch
exit
```

![Результат fastfetch](../images/lin2.png)