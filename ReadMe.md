Заготовка MySQL
===

Скачать шаблон:

> git clone https://github.com/itreviewchannel/template-docker-mysql your-folder-name

Запуск контейнера:

> docker-compose up -d

или

> docker-compose run --service-ports db

"db" - в данном случае это наименование блока в "docker-compose.yml".


**Подключение к MySQL с локальной машины**:

> mysql -h 127.0.0.1 -P 3306 -u root -p

Если будут появляться ошибки наподобие:

`ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)`

Попробуйте пересобрать контейнер:

> docker-compose up -d --build


**Подключение к MySQL из контейнера**:

Определяем наименование контейнера с MySQL:

>  docker-compose ps

Запускаем bash из контейнера:

> docker exec -it YOU_CONTAINER_NAME bash

Подключаемся к MySQL из контейнера:

> mysql -u root -p

Полезные ссылки:
-

* https://registry.hub.docker.com/_/mysql
* https://stackoverflow.com/questions/32360687/connect-to-docker-mysql-container-from-localhost
* https://itreviewchannel.ru/rabota-s-mysql-cherez-komandnuyu-stroku/
