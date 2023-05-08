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


        <aspectj.version>1.9.7</aspectj.version>
        <allure.version>2.15.0</allure.version>


        <dependency>
            <groupId>io.rest-assured</groupId>
            <artifactId>rest-assured</artifactId>
            <version>5.3.0</version>
        </dependency>

        <dependency>
            <groupId>io.qameta.allure</groupId>
            <artifactId>allure-junit4</artifactId>
            <version>${allure.version}</version>
        </dependency>
        <dependency>
            <groupId>io.qameta.allure</groupId>
            <artifactId>allure-rest-assured</artifactId>
            <version>${allure.version}</version>
        </dependency>
        <dependency>
            <groupId>com.github.javafaker</groupId>
            <artifactId>javafaker</artifactId>
            <version>1.0.2</version>
        </dependency>
        <dependency>
            <groupId>com.google.code.gson</groupId>
            <artifactId>gson</artifactId>
            <version>2.10.1</version>
            <scope>test</scope>
        </dependency>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.22.2</version>
                <configuration>
                    <testFailureIgnore>false</testFailureIgnore>
                    <argLine>
                        -javaagent:"${settings.localRepository}/org/aspectj/aspectjweaver/${aspectj.version}/aspectjweaver-${aspectj.version}.jar"
                    </argLine>
                    <properties>
                        <property>
                            <name>listener</name>
                            <value>io.qameta.allure.junit4.AllureJunit4</value>
                        </property>
                    </properties>
                    <systemProperties>
                        <property>
                            <name>allure.results.directory</name>
                            <value>${project.build.directory}/allure-results</value>
                        </property>
                    </systemProperties>
                </configuration>
                <dependencies>
                    <dependency>
                        <groupId>org.aspectj</groupId>
                        <artifactId>aspectjweaver</artifactId>
                        <version>${aspectj.version}</version>
                    </dependency>
                </dependencies>
            </plugin>
            <plugin>
                <groupId>io.qameta.allure</groupId>
                <artifactId>allure-maven</artifactId>
                <version>2.10.0</version>
                <configuration>
                    <reportVersion>2.15.0</reportVersion>
                </configuration>
            </plugin>
        </plugins>
        <pluginManagement>
            <plugins>
                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-surefire-plugin</artifactId>
                    <version>2.22.2</version>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>