Team 2 Docker Project

Docker арқылы жасалған екі контейнер: сайт (Nginx) және дерекқор (PostgreSQL).
Виртуалды машинада жұмыс істелген.(Ubuntu)
Желательно ссылкаларды виртуалды машинадан іске қоссаңыз.

Құрамы
Контейнер	Сипаттама	Порт
team2-site	Nginx негізіндегі веб-сайт	9090
team2-db-data	PostgreSQL дерекқоры (students кестесі)	5434
Сайт

Image жинау:

bash
docker build -t dilnaz1602/team2-site:1.0 .

Іске қосу:

bash
docker run -d -p 9090:80 --name team2-site dilnaz1602/team2-site:1.0

Браузерде ашу: http://localhost:9090

Дерекқор

Іске қосу:

bash
docker run -d -p 5434:5432 --name team2-db-data dilnaz1602/team2-db-data:1.0

Деректерді қарау:

bash
docker exec -it team2-db-data psql -U postgres -c "SELECT * FROM students;"
Пайдалы командалар
bash
docker ps                      # жұмыс істеп тұрған контейнерлер
docker rm -f team2-site        # контейнерді өшіру
docker images                  # image тізімі
Ескертпе

Автор
Dilnaz · Team 2
