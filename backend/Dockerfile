FROM python:3.10

WORKDIR /app

# Копируем requirements и устанавливаем зависимости
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Копируем код проекта
COPY . .

# Создаём директорию для сборщика статики
RUN mkdir -p /app/collected_static /app/media

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

# Команда запуска
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]