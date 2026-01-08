# Ansible homework: netology-ml

## Описание
Данный репозиторий содержит Ansible playbook для выполнения домашнего задания.

Playbook выполняет:
- проверку доступности хостов через ping
- обновление пакетного кеша
- установку набора пакетов
- копирование файла test.txt
- создание групп и пользователей с домашними директориями

---

## Структура проекта
├── inventory
├── homework.yaml
├── test.txt
└── README.md


---

## Требования
- Ansible установлен на управляющей машине
- На целевых хостах существует техническая учётная запись `ansible`
- У пользователя `ansible` настроен sudo без пароля

---

## Запуск playbook

```bash
ansible-playbook -i inventory homework.yaml


---

# 5️⃣ Лог выполнения playbook


```text
PLAY [netology-ml] *****************************************************

TASK [Ping hosts] ******************************************************
ok: [host1]
ok: [host2]

TASK [Update apt cache] ************************************************
changed: [host1]
changed: [host2]

TASK [Install required packages] **************************************
ok: [host1]
ok: [host2]

TASK [Copy test.txt to remote hosts] **********************************
changed: [host1]
changed: [host2]

TASK [Create user groups] *********************************************
changed: [host1] => (item=devops_1)
changed: [host1] => (item=test_1)
changed: [host2] => (item=devops_1)
changed: [host2] => (item=test_1)

TASK [Create users with home directories] *****************************
changed: [host1] => (item=devops_1)
changed: [host1] => (item=test_1)
changed: [host2] => (item=devops_1)
changed: [host2] => (item=test_1)

PLAY RECAP *************************************************************
host1 : ok=7  changed=4  unreachable=0  failed=0
host2 : ok=7  changed=4  unreachable=0  failed=0
