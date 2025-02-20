# Домашнее задание к занятию "`Базы данных, их типы`" - `Барышков Михаил`

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

*Приведите ответ в свободной форме.*

---
### Решение 1

Для решения задач крупной строительной компании, занимающейся проектированием, девелопментом и управлением данными, важно выбрать подходящие типы СУБД для каждой предметной области. Рассмотрим каждую задачу и предложим оптимальные решения.

 1.1 Бюджетирование проектов, финансовые отчёты и прогнозирование рисков

Тип СУБД: Реляционная СУБД (например, PostgreSQL, MySQL, Microsoft SQL Server).

Почему:
Реляционные СУБД обеспечивают чёткую структуру данных, поддерживают ACID-транзакции (целостность данных).
Подходят для сложных запросов, агрегации данных и формирования отчётов.
Имеют встроенные инструменты для аналитики и работы с финансовыми данными.

 1.1* Ускорение хеширования:
Для ускорения хеширования можно использовать специализированные API или библиотеки, такие как OpenSSL (для криптографических операций) или libsodium.
Если хеширование используется для аутентификации, можно рассмотреть использование специализированных сервисов, таких как AWS KMS или Google Cloud Key Management.

 1.2 Лендинги и CRM

Тип СУБД:
Для лендингов: NoSQL СУБД (например, MongoDB, Cassandra) — для гибкости и быстрой обработки данных.
Для CRM: Реляционная СУБД (например, PostgreSQL, Microsoft SQL Server) — для структурированного хранения данных о клиентах и транзакциях.

Почему:
NoSQL подходит для лендингов, так как данные могут быть неструктурированными (например, данные форм, поведенческие данные).
Реляционная СУБД для CRM обеспечивает целостность данных и поддержку сложных запросов.

 1.2* Использование одной СУБД:
Да, можно использовать PostgreSQL с поддержкой JSONB (для хранения неструктурированных данных лендингов) и реляционных таблиц (для CRM).
Альтернатива: MongoDB (если CRM не требует сложных транзакций).

 1.3  База корпоративных норм и правил

Тип СУБД: Реляционная СУБД (например, PostgreSQL, MySQL).

Почему:
Простая и понятная структура данных.
Поддержка иерархических данных (например, через таблицы с внешними ключами).
Удобство для хранения документов, нормативов и обучающих материалов.

 1.3* Использование существующей СУБД:
Да, можно использовать ту же СУБД, что и для бюджетирования (например, PostgreSQL).
Реализация: создать отдельную схему или таблицы для хранения корпоративных норм и правил.

 1.4 Логистика и маршрутизация

Тип СУБД: Графовая СУБД (например, Neo4j, Amazon Neptune).

Почему:
Графовые СУБД оптимизированы для работы со связями (например, маршруты, узлы, связи между объектами).
Позволяют быстро находить оптимальные маршруты и анализировать связи.

1.4* Подключение отдела закупок:
Да, можно использовать ту же графовую СУБД для логистики и закупок.
Реализация: добавить узлы и связи для данных о поставщиках, материалах и заказах.

 1.5* Использование одной СУБД для всех задач

Возможное решение: PostgreSQL с расширениями.

Почему:
PostgreSQL поддерживает реляционные данные, JSONB (для NoSQL-подобных задач), а также расширения для работы с графами (например, Apache AGE).
Универсальность и возможность масштабирования.
Подходит для бюджетирования, CRM, хранения корпоративных норм и даже логистики (с использованием графовых расширений).
Альтернатива: Использование нескольких специализированных СУБД (например, PostgreSQL для бюджетирования и CRM, MongoDB для лендингов, Neo4j для логистики).

Итоговые рекомендации:
Для бюджетирования и CRM: PostgreSQL.
Для лендингов: MongoDB (или JSONB в PostgreSQL).
Для корпоративных норм: PostgreSQL.
Для логистики: Neo4j (или Apache AGE в PostgreSQL).
Если требуется универсальное решение, PostgreSQL с расширениями может закрыть большинство задач. Однако для максимальной производительности и гибкости лучше использовать специализированные СУБД для каждой области.

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

*Приведите ответ в свободной форме.*

---

### Решение 2

Пополнение баланса счёта телефона (пошагово)
1.    Инициализация транзакции:
 -	Пользователь вводит номер телефона и сумму пополнения в интерфейсе приложения или платёжной системы.
 -	Система проверяет корректность введённых данных (номер телефона, сумма).
2.    Проверка баланса плательщика:
 -	Система проверяет, достаточно ли средств на счёте плательщика (банковская карта, электронный кошелёк и т.д.) для выполнения транзакции.
 -	Если средств недостаточно, транзакция прерывается, и пользователь получает уведомление.
3.    Блокировка средств:
 -	Если средств достаточно, система блокирует сумму пополнения на счёте плательщика (например, резервирует средства на карте).
4.    Пополнение баланса телефона:
 -	Система отправляет запрос оператору связи на пополнение баланса указанного номера телефона.
 -	Оператор связи подтверждает успешное зачисление средств.
5.    Списание средств у плательщика:
 -	После подтверждения от оператора связи система списывает заблокированную сумму с счёта плательщика.
6.    Завершение транзакции:
 -	Пользователь получает уведомление об успешном пополнении баланса.
 -	Система фиксирует транзакцию в журнале операций (логирование для отчётности и аудита).

Пополнение счёта телефона через автоплатёж*
1.    Инициализация автоплатежа:
 -	Пользователь заранее настраивает автоплатёж, указывая номер телефона, сумму и периодичность (например, ежемесячно).
2.    Проверка условий срабатывания:
 -	В указанный день система проверяет условия для выполнения автоплатежа (например, минимальный баланс на счёте плательщика).
3.    Блокировка средств:
 -	Если условия выполнены, система блокирует сумму пополнения на счёте плательщика.
4.    Пополнение баланса телефона:
 -	Система отправляет запрос оператору связи на пополнение баланса.
 -	Оператор связи подтверждает успешное зачисление средств.
5.    Списание средств у плательщика:
 -	После подтверждения от оператора система списывает заблокированную сумму с счёта плательщика.
6.    Уведомление пользователя:
 -	Пользователь получает уведомление об успешном выполнении автоплатежа.
 -	Система фиксирует транзакцию в журнале операций.

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

*Приведите ответ в свободной форме.*

---
### Решение 3

Пять преимуществ SQL-систем по отношению к NoSQL
1.    Чёткая структура данных:
 -	SQL-системы используют строгую схему данных (таблицы, строки, столбцы), что обеспечивает целостность и согласованность данных.
 -	Это особенно важно для финансовых, транзакционных и других критически важных систем.
2.    Поддержка ACID-транзакций:
 -	SQL-системы гарантируют атомарность, согласованность, изолированность и долговечность транзакций.
 -	Это делает их идеальными для приложений, где важна точность данных (например, банковские системы, электронная коммерция).
3.    Мощные возможности запросов:
 -	SQL предоставляет богатый язык запросов (JOIN, GROUP BY, агрегатные функции и т.д.), что позволяет выполнять сложные аналитические операции.
 -	Это упрощает формирование отчётов и анализ данных.
4.    Зрелость и экосистема:
 -	SQL-системы существуют десятилетиями, имеют огромное сообщество, документацию и инструменты для разработки и администрирования.
 -	Многие SQL-СУБД (например, PostgreSQL, MySQL) имеют открытый исходный код и активно развиваются.
5.    Интеграция с бизнес-приложениями:
 -	Большинство корпоративных приложений (ERP, CRM) изначально разработаны для работы с реляционными базами данных.
 -	SQL-системы легко интегрируются с существующими решениями.

Преимущества NewSQL систем перед SQL и NoSQL*

NewSQL — это современные системы, которые сочетают преимущества SQL и NoSQL. Их ключевые преимущества:
1.    Горизонтальная масштабируемость:
 -	NewSQL системы (например, CockroachDB, Google Spanner) поддерживают горизонтальное масштабирование, как NoSQL, но при этом сохраняют ACID-гарантии, как SQL.
 -	Это позволяет обрабатывать большие объёмы данных с высокой производительностью.
2.    Высокая производительность:
 -	NewSQL оптимизированы для работы с большими данными и высоконагруженными приложениями.
 -	Они используют распределённые архитектуры, что позволяет обрабатывать запросы быстрее, чем традиционные SQL-системы.
3.    Поддержка ACID-транзакций в распределённых системах:
 -	В отличие от NoSQL, NewSQL гарантирует ACID-транзакции даже в распределённых средах.
 -	Это критически важно для финансовых и транзакционных систем.
4.    Совместимость с SQL:
 -	NewSQL системы поддерживают стандартный SQL, что упрощает миграцию с традиционных SQL-СУБД.
 -	Разработчики могут использовать знакомые инструменты и запросы.
5.    Упрощённое управление:
 -	NewSQL системы часто имеют встроенные механизмы для автоматического шардирования, репликации и восстановления после сбоев.
 -	Это снижает нагрузку на администраторов баз данных.
6.    Гибкость:
 -	NewSQL сочетает структурированность SQL с гибкостью NoSQL, что позволяет использовать их для различных типов данных и сценариев.

Итог:

- SQL идеален для структурированных данных, сложных запросов и транзакций.

- NoSQL подходит для неструктурированных данных и высоконагруженных систем, но жертвует ACID-гарантиями.

 -NewSQL объединяет лучшее из двух миров: масштабируемость NoSQL и надёжность SQL, что делает их перспективным выбором для современных распределённых приложений.

----

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*

---

### Решение 4

Критерии выбора типа СУБД

Для задачи, требующей обработки огромного количества данных на 1000 машинах, ключевыми критериями выбора СУБД будут:
1.    Горизонтальная масштабируемость:
 -	Система должна эффективно распределять данные и вычисления между множеством узлов (машин).
 -	Это позволяет обрабатывать большие объёмы данных с высокой производительностью.
2.    Поддержка распределённых вычислений:
 -	СУБД должна поддерживать параллельную обработку данных и распределённые запросы.
 -	Это важно для выполнения сложных вычислений на больших данных.
3.    Отказоустойчивость и высокая доступность:
 -	Система должна обеспечивать репликацию данных и автоматическое восстановление после сбоев.
 -	Это критически важно для работы в распределённой среде.
4.    Производительность:
 -	СУБД должна минимизировать задержки при обработке запросов и вычислениях.
 -	Это особенно важно для задач, требующих быстрого анализа данных.
5.    Гибкость модели данных:
 -	В зависимости от типа данных (структурированные, полуструктурированные, неструктурированные) может потребоваться поддержка различных моделей данных (реляционная, документная, графовая и т.д.).
6.    Экономическая эффективность:
 -	Система должна быть рентабельной при масштабировании на 1000 машин (например, использование open-source решений или облачных сервисов с гибкой тарификацией).


Модель распределённых вычислений

Для данной задачи лучше всего подойдёт модель MapReduce или её современные аналоги (например, Apache Spark). Вот почему:
1.    MapReduce:
 ####	Преимущества:
 - Идеально подходит для обработки больших данных на распределённых кластерах.
 - Позволяет разбивать задачи на мелкие подзадачи (map) и агрегировать результаты (reduce).
 - Обеспечивает отказоустойчивость за счёт повторного выполнения задач на других узлах в случае сбоя.
 ####	Недостатки:
 - Высокие накладные расходы на дисковые операции (медленнее по сравнению с in-memory системами).
2.    Apache Spark:
 ####	Преимущества:
 - Использует in-memory вычисления, что значительно ускоряет обработку данных по сравнению с MapReduce.
 - Поддерживает сложные pipelines обработки данных (ETL, машинное обучение, потоковая обработка).
 - Имеет богатый набор библиотек (Spark SQL, MLlib, GraphX).
 ####	Недостатки:
 -  Требует больших объёмов оперативной памяти.

Тип СУБД

Для работы с большими данными и распределёнными вычислениями лучше всего подойдут:
1.    NoSQL СУБД:
 -  Примеры: Apache Cassandra, MongoDB, Amazon DynamoDB.
 -	Почему: Они обеспечивают горизонтальную масштабируемость, высокую производительность и отказоустойчивость.
 -	Применение: Для хранения и обработки неструктурированных или полуструктурированных данных.
2.    NewSQL СУБД:
 -	Примеры: CockroachDB, Google Spanner.
 -	Почему: Они сочетают горизонтальную масштабируемость NoSQL с поддержкой ACID-транзакций и SQL-запросов.
 -	Применение: Для структурированных данных, где важна целостность и согласованность.
3.    СУБД для аналитики:
 -	Примеры: Apache HBase, ClickHouse.
 -	Почему: Они оптимизированы для выполнения сложных аналитических запросов на больших данных.
 -	Применение: Для задач, связанных с аналитикой и формированием отчётов.

Итоговая рекомендация

Для задачи с 1000 машин и большими объёмами данных:
 - Используйте Apache Spark для распределённых вычислений (высокая производительность и гибкость).
 - Выберите NoSQL СУБД (например, Apache Cassandra) или NewSQL СУБД (например, CockroachDB) в зависимости от типа данных и требований к транзакциям.
 - Если требуется аналитика, добавьте ClickHouse для выполнения сложных запросов.
Такой подход обеспечит высокую производительность, масштабируемость и отказоустойчивость.
