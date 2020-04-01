# OTUS Linux Security
## Установка зависимостей
```bash
vagrant plugin install vagrant-docker-compose
```
## Использование
```bash
vagrant up
cat audit.log
```
## Результаты аудита
```bash
#cat audit.log | grep WARN
[WARN] 1.2.1 - Ensure a separate partition for containers has been created
[WARN] 4.6  - Ensure that HEALTHCHECK instructions have been added to container images
[WARN]      * No Healthcheck found: [python:3-alpine]
[WARN] 5.11  - Ensure CPU priority is set appropriately on the container
[WARN]      * Container running without CPU restrictions: vagrant_server_1
[WARN] 5.12  - Ensure that the container's root filesystem is mounted as read only
[WARN]      * Container running with root FS mounted R/W: vagrant_server_1
[WARN] 5.28  - Ensure that the PIDs cgroup limit is used
[WARN]      * PIDs limit not set: vagrant_server_1
```
1.2.1 - /var/lib/docker монтируется на отдельный диск.
4.6 - Для контейнера настроен HEALTHCHECK в compose, ошибка относится к базовому образу.
5.11 - Проверяет параметр cpu-shares. В 3 версии docker-compose этот параметр был заменен на cpus, поэтому не проходит проверку.
5.12 - не удалось запустить контейнер с параметром read-only
5.28 - pids_limit не работает в 3 версии docker-compose
