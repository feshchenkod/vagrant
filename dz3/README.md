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
[WARN] 1.2.1 - Ensure a separate partition for containers has been created
[WARN] 4.6  - Ensure that HEALTHCHECK instructions have been added to container images
[WARN]      * No Healthcheck found: [python:3-alpine]
[WARN] 5.2  - Ensure that, if applicable, SELinux security options are set
[WARN]      * No SecurityOptions Found: vagrant_server_1
[WARN] 5.10  - Ensure that the memory usage for containers is limited
[WARN]      * Container running without memory restrictions: vagrant_server_1
[WARN] 5.11  - Ensure CPU priority is set appropriately on the container
[WARN]      * Container running without CPU restrictions: vagrant_server_1
[WARN] 5.12  - Ensure that the container's root filesystem is mounted as read only
[WARN]      * Container running with root FS mounted R/W: vagrant_server_1
[WARN] 5.13  - Ensure that incoming container traffic is bound to a specific host interface
[WARN]      * Port being bound to wildcard IP: 0.0.0.0 in vagrant_server_1
[WARN] 5.14  - Ensure that the 'on-failure' container restart policy is set to '5'
[WARN]      * MaximumRetryCount is not set to 5: vagrant_server_1
[WARN] 5.25  - Ensure that the container is restricted from acquiring additional privileges
[WARN]      * Privileges not restricted: vagrant_server_1
[WARN] 5.28  - Ensure that the PIDs cgroup limit is used
[WARN]      * PIDs limit not set: vagrant_server_1
```
