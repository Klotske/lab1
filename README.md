# Лабораторная работа  №1

### Задание
Написать программу на Python, которая:

* Подсчитывает общее количество символов в файле
* Подсчитывает общее количесто символов без пробелов
* Подсчитывает количество символов без знаков препинания
* Подсчитывает количество слов в файле
* Подсчитывает количество предложений
* Результат подсчета должен быть выведен в консоль

**Вход программы:**
Файл `steam_description_data.csv`

**Выход программы:**
Информация о количестве символов, слов и предложений

> **_ВАЖНО:_**
Результат оформить в виде репозитория на гитхабе.

### Решение:
* Для чтения файла используется модуль csv
* Получившийся при чтении файла список записей вновь склеивается в одну строку
* Длинна строки определяется при помощи функции len()
* При помощи метода строки count() находится количество пробелов, знаков препинания
* Используя модуль re производится поиск слов и предложений:
    1. Слова находятся при помощи паттерна: `(\w+'\w+)|(\w+-\w+'\w+)|(\w+-\w+'\w)|\w+`
    2. Предложения определяются при помощи паттерна: `([A-Z][^\.!?]*[\.!?])`
* Производится поиск всех совпадений при помощи метода re.findall()
* Количество найденных слов и предложений определяется при помощи функции len()