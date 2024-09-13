Подготовка тестового окружения для запуска автотестов.
Установить приложения
Intelij IDEA 2022.3.2 (Community Edition)
Docker Desktop
Chromedriver Version: 118.0.5993.70
Браузер: Chrome Версия 118.0.5993.89 (Официальная сборка), (64 бит)
DBeaver 23.2.2
Процедура запуска тестов
Запускаем Docker Desktop
Запускаем IDEA
В терминале IDEA набираем docker compose down
Ждем удаления 3 контейнеров и набираем docker compose up
Ждем запуска контейнеров node-app, mysql, postgres и во 2ом терминале для
запуска джарника набираем java -jar ./artifacts/aqa-shop.jar
В 3ем терминале запускаем тесты командой ./gradlew clean test --info
Для генерации отчетов на Allure после прохождения тестов набираем в терминале ./gradlew allureserve
По умолчанию в файле application.properties указано подключение к MySQL Для замены СУБД на PostgreSQL необходимо заменить строку 3 на
spring.datasource.url=jdbc:postgresql://localhost:5432/app и затем также запусить тесты согласно
пунктам 3-6
Для отключения джарника или остановки контейнеров нажать ctrl+C