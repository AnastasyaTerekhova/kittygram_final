# kittygram
Сайт, куда можно выкладывать фотки котиков и их достижения. Бэкенд написан на Django. Проект предназначен для того, чтобы познакомится с Docker (проект упакован в контейнеры) и научится настраивать CI/CD

# Как подключить:
Клонировать репозиторий и перейти в него в командной строке:
```bash
git clone https://github.com/AnastasyaTerekhova/kittygram_final.git
cd kittygram_final/backend
```

В локальной папке проекта создать и активировать виртуальное окружение:
```bash
# Команды для Windows:
python -m venv env
source env/Scripts/activate

# Команды для Linux и macOS:
python3 -m venv env
source env/bin/activate
```

Обновить пакетный менеджер:
```bash
python -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:
```bash
pip install -r requirements.txt
```

Выполнить команды:
```bash
cd kittygram_final
docker compose up -d
docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/collected_static/. /static/