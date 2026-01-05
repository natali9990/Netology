# Netology ML Docker Container

## Описание
Контейнер на базе `continuumio/miniconda3`, который:
- содержит рабочую директорию `/app`
- запускает shell-скрипт `1.sh`
- выводит сообщение "Hello Netology"
- включает python-пакеты:
  - mlflow
  - boto3
  - pymysql

## Сборка образа

```bash
docker build -t netology-ml:netology-ml .
