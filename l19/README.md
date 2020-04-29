## Wazuh
------
### Настройка active response на брутфорс ssh в wazuh
В wazuh уже имеются готовые скрипты для active response, находятся в каталоге /var/ossec/active-response/bin/. Для автоматической блокировки атакующего ip в файл /var/ossec/etc/ossec.conf необходимо бовавить правило:
```bash
<active-response>
    <command>firewall-drop</command>
    <location>local</location>
    <rules_id>5716</rules_id>
    <timeout>1800</timeout>
</active-response>
```
**firewall-drop** - название скрипта, **rules id** - идентификатор события безопасности "sshd: authentication failed.".

При данной натсройке блокировка будет производиться только на хосте, который подвержен атаке.
