# Базовый образ
FROM continuumio/miniconda3:latest

# Рабочая директория
WORKDIR /app

# Копируем скрипт
COPY 1.sh /app/1.sh

# Даём права на исполнение
RUN chmod +x /app/1.sh

# Устанавливаем python-пакеты
RUN pip install --no-cache-dir mlflow boto3 pymysql

# Запуск контейнера
CMD ["/app/1.sh"]
