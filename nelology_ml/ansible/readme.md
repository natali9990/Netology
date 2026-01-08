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
PLAY [netology-ml] *****************************************************************************************************

TASK [Gathering Facts] *************************************************************************************************
ok: [localhost]

TASK [Ping hosts] ******************************************************************************************************
ok: [localhost]

TASK [Update apt cache] ************************************************************************************************
changed: [localhost]

TASK [Install required packages] ***************************************************************************************
ok: [localhost]

TASK [Copy test.txt to remote hosts] ***********************************************************************************
changed: [localhost]

TASK [Create user groups] **********************************************************************************************
changed: [localhost] => (item=devops_1)
changed: [localhost] => (item=test_1)

TASK [Create users with home directories] ******************************************************************************
changed: [localhost] => (item=devops_1)
changed: [localhost] => (item=test_1)

PLAY RECAP *************************************************************************************************************
localhost                  : ok=7    changed=4    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

ansible@compute-vm-4-16-60-ssd-1751297344083:~/Netology/nelology_ml/ansible$

PLAY RECAP *************************************************************
host1 : ok=7  changed=4  unreachable=0  failed=0
host2 : ok=7  changed=4  unreachable=0  failed=0
