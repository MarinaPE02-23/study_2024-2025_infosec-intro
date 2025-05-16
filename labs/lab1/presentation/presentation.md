---
## Front matter
lang: ru-RU
title: "Основы информационной безопасности"
author:
  - Воробьев Д.П.
institute:
  - Российский университет дружбы народов, Москва, Россия
  
## i18n babel
babel-lang: russian
babel-otherlangs: english

## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---


# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Воробьев Данил Павлович
  * Студент группы НБИ 02-23
  * Российский университет дружбы народов
:::
::::::::::::::

## Преподаватель

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Кулябов Дмитрий Сергеевич
  * д.ф.-м.н., профессор
  * профессор кафедры прикладной информатики и теории вероятностей
  * Российский университет дружбы народов
:::
::::::::::::::



# "Ошибки проверки вводимых данных: инъекция E-mail"

# Актуальность проблемы

## Почему это важно?


    32% уязвимостей связаны с валидацией ввода (OWASP, 2023)

    80% атак начинаются с компрометации email (Verizon DBIR)

# Виды атак (инфографика)

## 3 главные угрозы


    SQL-инъекция → Утечка данных

    XSS → Кража сессий

    CRLF-инъекция → Спам-рассылки


# SQL-инъекция

## Пример взлома через email
Код:
sql

SELECT * FROM users WHERE email = 'admin@test' OR 1=1 --'



# XSS-атака

## Межсайтовый скриптинг

Пример:
html

user@test"><script>stealCookies()</script>


# Подделка заголовков

## CRLF-инъекция в SMTP
Пример:

test@mail.com%0ACc: victim@bank.com


## Методы защиты

Заголовок: Как предотвратить атаки?
Чек-лист:
✔ Валидация по RFC 5322
✔ Подготовленные SQL-запросы
✔ HTML-экранирование
✔ Фильтрация CRLF


# Реальный кейс

## Взлом Roundcube (2022)
Данные:

    CVE-2022-30307

    Рассылка спама через инъекцию

# Инструменты защиты

## Что использовать?

Список:

    OWASP ZAP для тестирования

    Библиотеки: Apache Commons Validator

    CSP для защиты от XSS


# Заключение

## Главные выводы

Тезисы:

    Email — критичное поле для атак

    Требуется многоуровневая защита

    Регулярный аудит обязателен
    Призыв:
    "Проверьте свои формы сегодня!"


