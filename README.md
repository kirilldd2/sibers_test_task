Комментарии по запуску:

Самый простой способ запуска - через Docker.
Единственное что нужно - удалить лишний файл в папке /initdb. create_tables_admin.sql при первом запуске контейнера создаст таблицы и 2 админов. create_tables_many.sql в дополнение к этому создаст 300 сгенерированных пользователей. Нужно выбрать один: create_tables_admin.sql без пользователей, create_tables_many.sql с пользователями, а другой удалить.

Далее нужно прописать `docker-compose up -d` и сайт должен быть доступен на http://localhost.

Все параметры для подключения к БД находятся в файле .env и специально оставлены в проекте.

Данные админов:
1. admin admin1234
2. admin2 admin1234