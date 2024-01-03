# Базовый образ для документации
FROM alpine:latest

# Выполнение предустановки пакетов
RUN apk --no-cache add make git python3 py3-pip

# Копирование проекта в контейнер
COPY . /project

# Установка зависимостей
RUN cd /project && pip3 install -r requirements.txt

# Установка Sphinx и необходимых плагинов
RUN pip3 install sphinx recommonmark sphinx_rtd_theme

# Установка других необходимых пакетов
RUN apk --no-cache add build-base

# Запуск генерации документации
CMD cd /project && make html