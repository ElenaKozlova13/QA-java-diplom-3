# QA-java-diplom-3
## О проекте
Тестирование UI веб-приложения учебного сервиса [Stellar Burgers](https://stellarburgers.nomoreparties.site/)
Тестовые данные создаются и удаляются через API [Документации API](https://code.s3.yandex.net/qa-automation-engineer/java/cheatsheets/paid-track/diplom/api-documentation.pdf)
### Цели:
- Протестировать необходимую функциональность
- Подключить браузеры Google Chrome и Яндекс.Браузер
- Использовать Page Object
- Сформировать отчёт Allure

## Используемые инструменты
- Java 11
- maven 4.0.0
- JUnit 4.13.2
- selenium 4.8.1
- webdriver manager 5.3.2
- rest-assured 5.3.0
- allure 2.15.0
- maven-surefire-plugin 2.22.2
- gson 2.10.1
- javafaker 1.0.2

## Запуск тестов и построение отчёта:
- mvn clean test
- mvn allure:serve