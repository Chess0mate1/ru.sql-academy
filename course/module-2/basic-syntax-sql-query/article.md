# Базовый синтаксис SQL запроса

Одна из основных функций SQL — это получение выборок данных из СУБД.
Для этого в SQL используется оператор `SELECT`. Давайте рассмотрим несколько простых запросов с его участием.

## Вывод произвольных значений

Для начала важно понимать, что через оператор `SELECT` можно выводить данные не только из таблиц базы данных,
но и произвольные строки, числа, даты и т.д. Например, так можно вывести произвольную строку:

```sql
SELECT "Hello world"
```

## Вывод всех данных из таблицы

Для вывода всех полей из определённой таблицы используется символ `*`. Давайте взглянем на схему базы данных и
выведем данные одной из таблиц.

<ERD databaseName="Family" />

```sql
SELECT * FROM FamilyMembers
```

| member_id | status   | member_name       | birthday             |
| --------- | -------- | ----------------- | -------------------- |
| 1         | father   | Headley Quincey   | 1960-05-13T00:00:00Z |
| 2         | mother   | Flavia Quincey    | 1963-02-16T00:00:00Z |
| 3         | son      | Andie Quincey     | 1983-06-05T00:00:00Z |
| 4         | daughter | Lela Quincey      | 1985-06-07T00:00:00Z |
| 5         | daughter | Annie Quincey     | 1988-04-10T00:00:00Z |
| 6         | father   | Ernest Forrest    | 1961-09-11T00:00:00Z |
| 7         | mother   | Constance Forrest | 1968-09-06T00:00:00Z |

## Вывод данных из определённых колонок таблицы

Если необходимо вывести информацию только по определённым столбцам таблицы, а не всю сразу, то
это можно сделать перечисляя названия столбцов через запятую:

```sql
SELECT member_id, member_name FROM FamilyMembers
```

| member_id | member_name       |
| --------- | ----------------- |
| 1         | Headley Quincey   |
| 2         | Flavia Quincey    |
| 3         | Andie Quincey     |
| 4         | Lela Quincey      |
| 5         | Annie Quincey     |
| 6         | Ernest Forrest    |
| 7         | Constance Forrest |

## Псевдонимы

В случае, если мы хотим вывести какие-то столбцы таблицы, но чтобы в итоговой выборке они были названы иначе,
мы можем использовать псевдонимы (их также называют алиасами).

Их синтаксис достаточно простой, мы должны использовать оператор `AS`. Как в примере ниже:

```sql
SELECT member_id, member_name AS Name FROM FamilyMembers
```

| member_id | Name              |
| --------- | ----------------- |
| 1         | Headley Quincey   |
| 2         | Flavia Quincey    |
| 3         | Andie Quincey     |
| 4         | Lela Quincey      |
| 5         | Annie Quincey     |
| 6         | Ernest Forrest    |
| 7         | Constance Forrest |

Или же можно обойтись и без него, просто написав желаемое наименование поля через пробел.

```sql
SELECT member_id, member_name Name FROM FamilyMembers
```

> Псевдонимы могут содержать до 255 знаков (включая пробелы, цифры и специальные символы)

## Самостоятельные упражнения

Это наш первый урок практического модуля. До этого были лишь теоретические, направленные на восполнение потенциальных пробелов в теории реляционных баз данных.
После каждого практического урока мы предлагаем группу заданий для самостоятельной работы, чтобы сразу же закрепить полученную информацию.

Если вы пропустили модуль «Введение», а именно статью <a href="https://sql-academy.org/ru/guide/intro-structure-of-course" target="_blank"> «Структура курса» </a>, где описывался принцип работы и интерфейс блока
«Самостоятельные упражнения», то рекомендуем <a href="https://sql-academy.org/ru/guide/intro-structure-of-course" target="_blank"> вернуться к нему </a>.
