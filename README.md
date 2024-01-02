# GraduateWorkFormatter (Корректор диплома)

## Авторы:
Лопарёв Влад *(Flask-приложение)*
Кирсанова Екатерина *(работа с исходным кодом, changelog)*
Пименов Максим *(проверка оформления ссылок в соответствие ГОСТ)*

## Описание:
Сервис автоматической проверки формальных требований к оформлению текстов дипломных работ на мат-мехе и исправления до нужных требований.
В прошлом году Александр Горбатов сделал основную часть https://github.com/SilversShade/GraduateWorkFormatter.
Необходимо было исправить тонкие моменты. Например, проверить, что ссылки оформлены по ГОСТ и исправить это, если не так.
К тому же, изначально это было консольной утилитой. Сейчас это web-сервис.

## Подробности реализации:
Web-сервис построен как Flask-приложение.
Исходный проект был использован как модуль Flask-приложения (скрипт), выполняющий основную работу.
Для этого была изменена структура .py файлов проекта.
Также был переработан весь исходный код, чтобы добавить список изменений каждого файла, обработанного скриптом (changelog).

Все файлы, загруженные клиентом, а также обработанные файлы и changelog'и хранятся в закодированном виде в /uploads.
Кодирование происходит с помощью приписывания к исходному имени файла текущего времени (библиотека time).
При скачивании клиентом обработанного файла, имя файла декодируется и выглядит так: "edited_исходное_имя_файла.расширение_файла".
