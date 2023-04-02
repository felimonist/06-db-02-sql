Задание 1.

 ```
version: '3'

services:
  database:
    image: postgres:12
    ports:
      - 5432:5432
    environment:
      POSTGRES_USER: felimonist
      POSTGRES_PASSWORD: 515253
      POSTGRES_DB: feli_db_
    volumes:
      - ./db-data/:/var/lib/postgresql/data/
      - ./db-backup/:/Work/BackUp/
```

![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/1.JPG)

Задание 2.

![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/2.JPG)


![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/2.1.JPG)


![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/2.2.JPG)

Задание 3.

![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/3.JPG)

Задание 4.

![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/4.JPG)

Задание 5.

![slave](https://github.com/felimonist/06-db-02-sql/blob/main/img/5.JPG)

 Значение 0.00 — затраты на получение первой строки, 18.10 - затраты на получение всех строк, rows - число строк, которое должено вывестесь. width - средний размер строк в байтах. Каждая запись сравнивается с условием "заказ" IS NOT NULL.
 
Задание 6.

pg_dump -U felimonist test_db > /Work/BackUp/test_db.backup

sudo docker stop 6e6c045b5649

docker run --rm -d -e POSTGRES_USER=test_admin_user -e POSTGRES_PASSWORD=515253 -e POSTGRES_DB=test_db -v /home/felimonist/Netology/virt-homeworks/06-db-02-sql/db-backup:/Work/feli_backup --name feli_pg12 postgres:12


export PGPASSWORD=515253 && psql -h localhost -U test_admin_user -f /Work/feli_backup/test_db.backup test_db


