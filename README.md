Комментарии по запуску:

Самый простой способ запуска - через Docker.
Единственное что нужно - удалить лишний файл в папке /initdb. create_tables_admin.sql при первом запуске контейнера создаст таблицы и 2 админов. create_tables_many.sql в дополнение к этому создаст 300 сгенерированных пользователей. Нужно выбрать один: create_tables_admin.sql без пользователей, create_tables_many.sql с пользователями, а другой удалить. (Так как дата рождения сгенерирована случайно, а для даты рождения установлено ограничение на клиенте - возраст 10 лет, то при изменении существующих записей может появляться предупреждение и для сохранение потребуется изменить дату рождения на более раннюю)

Далее нужно прописать `docker-compose up -d` и сайт должен быть доступен на http://localhost.

Все параметры для подключения к БД находятся в файле .env и специально оставлены в проекте.

Данные админов:
1. admin admin1234
2. admin2 admin1234

Были использованы следующие дополнительные технологии:
- PDO - для соединения с БД
- jQuery + AJAX - для создания анимаций и выполнения сортировки, добавления и удаления без перезагрузки страницы
- Bootstrap 5  - для верстки
- Docker - для создания среды разработки и запуска
