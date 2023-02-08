# Домашнее задание к занятию 12.1 "Базы данных." - "Червяков Антон"


---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

```
Сотрудники (
   
   - ID сотрудника [INTEGER, PRIMARY KEY, UNIQUR INDEX]
   - Фамилия Сотрудника [NVARCHAR(255)]
   - Имя Сотрудника [NVARCHAR(255)]
   - Отчество Сотрудника [NVARCHAR(255)]
   - ID Должности [INTEGER]
   - Дата найма [DATE]
   - ID Филиала [INTEGER]
)

Должности (
   - ID Должности [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - ID Структурного подразделения [INTEGER]
   - Должность [NVARCHAR(255)]
)

Типы подразделений (
   - ID Типа подразделения [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - Тип подразделения [NVARCHAR(255)]
)

Проекты (
   - ID Проекта [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - Название проекта [NVARCHAR(255)]
)

Прикрепление к проектам (
   - ID Прикрепления [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - ID Проекта [INTEGER]
)

Структурные подразделения (
   - ID Структурного подразделения [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - ID Типа подразделения [INTEGER]
   - Название структурного подразделения [NVARCHAR(255)]
)

Город (
   - ID Города [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - Город [NVARCHAR(255)]
)

Филиал (
   - ID Филиала [INTEGER, PRIMARY KEY, UNIQUE INDEX]
   - ID Города [INTEGER]
   - Адреc [NVARCHAR(255)]
)

```
