# Ansible role: elasticsearch
Разворачивает эластик в докер контейнере
## Переменные
При использовании этой роли в плейбуках, должны быть заданы переменные:

    elastic_password:  # пароль пользователя elastic (зашифрованный vars/vault.yml в примере)
    
## Сертификаты
Для работы SSL нужны сертификаты и ключи. При работе в составе плейбука они должны лежать в директории `files/certs`, откуда роль из возьмет

## Пример плейбука

    ---
    - hosts: elastic
      become: true
      vars_files:
        - vars/vault.yml
      roles:
        - elasticsearch
      tags:
        - elastic
