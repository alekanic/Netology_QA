# Процедура запуска автотестов

1. Клонировать репозиторий командой: `git clone https://github.com/alekanic/Diploma.git`
2. Из ./src в скаченном репозитории, запустить Docker командой `docker compose up -d`

## Для MySQL

1. Запустить приложение-эмулятор банковских сервисов на MySQL:\
`java -jar .\artifacts\aqa-shop\aqa-shop.jar --spring.datasource.url=jdbc:mysql://localhost:3306/app`\
2. Запустить авто-тесты командой в консоли:
`.\gradlew clean test -DdbUrl=jdbc:mysql://localhost:3306/app`

## Для PostgreSQL

1. В терминале №1 запустить приложение-эмулятор банковских сервисов на PostgreSQL:\
`java -jar .\artifacts\aqa-shop\aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app`
2. В терминале №2 запустить авто-тесты командой в консоли:
`.\gradlew clean test -DdbUrl=jdbc:postgresql://localhost:5432/app`

## Создание отчета Allure

+ Ввести следующую команду в терминале:
`.\gradlew allureServe`