# OTUS Linux Security
## Заупст nginx на нестандартном порту
### Способ 1
С помощью setsebool перевести параметр nis_enabled в состояние on и перезапустить nginx
```bash
vagrant up centos1
curl -s 127.0.0.1:8081
```
### Способ 2
Добавить с помощью semanage в имеющийся тип http_port_t новый порт и перезапустить nginx
```bash
vagrant up centos2
curl -s 127.0.0.1:8082
```
### Способ 3
Создание selinux-модуля для nginx с помощью sepolgen
```bash
vagrant up centos3
curl -s 127.0.0.1:8083
```
