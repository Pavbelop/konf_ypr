Dependency Visualizer

![Header1](https://github.com/go1x1loh/dsconfig/blob/main/hw2/output/graph.png)


Dependency Visualizer — это инструмент для анализа зависимостей Maven-пакетов и генерации графов зависимостей с использованием PlantUML.
Общее описание

Этот проект позволяет:

    Загружать POM-файлы пакетов из Maven-репозитория.
    Рекурсивно анализировать зависимости до заданной глубины.
    Генерировать визуализацию зависимостей в формате PlantUML.
    Создавать графическое представление зависимостей в формате PNG.

Описание функций
Основные функции

    Загрузка POM-файлов
    Функция fetch_pom загружает POM-файл из указанного Maven-репозитория по заданным groupId, artifactId и версии.

    Парсинг зависимостей
    Функция parse_pom извлекает зависимости (группу, артефакт и версию) из содержимого POM-файла.

    Рекурсивный сбор зависимостей
    Функция collect_dependencies строит дерево зависимостей до указанной глубины.

    Генерация PlantUML-диаграммы
    Класс GraphVisualizer создает PlantUML-файл, который можно использовать для построения графа зависимостей.

    Визуализация графа
    Функция visualize выполняет генерацию графического файла (PNG) из PlantUML-файла с использованием PlantUML JAR.

Настройка
Установка зависимостей

    Убедитесь, что Python версии ≥3.7 установлен.
    Установите необходимые пакеты:

    pip install requests

Загрузка PlantUML

Скачайте PlantUML JAR-файл с официального сайта и убедитесь, что Java установлена в системе.
Использование
Пример команды

Запустите анализатор с указанием Maven-репозитория, пакета, глубины анализа и пути к PlantUML:

python main.py --repo-url "https://repo1.maven.org/maven2" \
               --package "org.springframework:spring-core:5.3.25" \
               --depth 3 \
               --plantuml-path "/path/to/plantuml.jar" \
               --output-path "./output"

Аргументы

    --repo-url: URL Maven-репозитория.
    --package: Пакет в формате group:artifact:version.
    --depth: Максимальная глубина анализа зависимостей.
    --plantuml-path: Путь к JAR-файлу PlantUML.
    --output-path: Папка для сохранения графов.
