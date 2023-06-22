# Дипломный проект по профессии «Тестировщик»
## Документы
* [План автоматизации](https://github.com/KseniyaLazareva/diplom/blob/main/Plan.md)
* [Отчет по итогам автоматизации](https://github.com/KseniyaLazareva/diplom/blob/main/Summary.md)
* [Отчет по итогам тестирования](https://github.com/KseniyaLazareva/diplom/blob/main/Report.md)

Для запуска должны быть установлены:
* IntelliJ IDEA
* Docker Desktop

Процедура запуска автотестов:
1. Используя команду `git clone` скопировать [Дипломный проект](https://github.com/KseniyaLazareva/diplom)
2. Запустить Docker Desktop
3. Открыть проект в IntelliJ IDEA
4. Используя команду `docker-compose up -d` запустить контейнеры с  MySQL , PostgreSQL и Node.js
5. Для запуска SUT ввести следующую команду:
6. - для MySQL: `java -jar artifacts/aqa-shop.jar -port=8080`
7. - для PostgreSQL: `java -Dspring.datasource-postgresql.url=jdbc:postgresql://localhost:5432/app -jar artifacts/aqa-shop.jar`
8. Для запуска автотестов ввести: `./gradlew clean test`. Для PostgreSQL необходимо сначала выполнить настройку в **DBHelper**. Необходимо закоментировать блок кода Connection с настройками для MySQL(18-20 строки) и раскоментировать блок с настройками для PostgreSQL(22-24 строки)
9. Для создания отчета Allure ввести:  `./gradlew allureServe`  
