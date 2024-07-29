# Домашнее задание к занятию «Репликация и масштабирование. Часть 2»

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.

---

### Задание 1

Опишите основные преимущества использования масштабирования методами:

- активный master-сервер и пассивный репликационный slave-сервер; 
~Высокая доступность - если активный master-сервер выходит из строя, репликационный slave-сервер может быстро стать новым мастером и обеспечить непрерывную работу системы.
~Резервное копирование - slave-сервер может использоваться для создания резервных копий данных без влияния на производительность активного сервера.
~Распределение нагрузки чтения - чтение запросов может быть перенаправлено на slave-серверы, что позволяет балансировать нагрузку и повышать производительность системы.
- master-сервер и несколько slave-серверов;
~Горизонтальное масштабирование - позволяет распределить нагрузку между несколькими slave-серверами, что позволяет обрабатывать больше запросов и увеличивать пропускную способность системы.
~Повышенная отказоустойчивость - если один из slave-серверов выходит из строя, другие серверы могут продолжать работу, обеспечивая непрерывность работы системы.
~Резервное копирование - каждый slave-сервер может использоваться для создания независимых резервных копий данных.
- активный сервер со специальным механизмом репликации — distributed replicated block device (DRBD);
~Высокая отказоустойчивость - обеспечивает синхронную репликацию данных между активным и пассивным узлами, что позволяет обнаруживать и восстанавливаться от сбоев без потери данных.
~Мгновенное восстановление - в случае сбоя активного сервера, пассивный узел может мгновенно стать активным и продолжать обслуживать запросы без необходимости перезагрузки системы.
~Простота администрирования - предоставляет прозрачное хранилище данных и абстрагируется от сложностей настройки и управления репликацией на уровне приложений.
- SAN-кластер.
~Высокая отказоустойчивость - обеспечивает репликацию данных и обнаружение сбоев, позволяя системе продолжать работу даже при выходе из строя одного из узлов.
~Высокая производительность - может обеспечивать высокую производительность и пропускную способность благодаря использованию специализированных хранилищ данных и оптимизированных сетей.
~Общее хранилище данных - позволяет разделить ресурсы хранилища между несколькими серверами, обеспечивая централизованное управление и распределение данных.

*Дайте ответ в свободной форме.*

---

### Задание 2


Разработайте план для выполнения горизонтального и вертикального шаринга базы данных. База данных состоит из трёх таблиц: 

- пользователи, 
- книги, 
- магазины (столбцы произвольно). 

Опишите принципы построения системы и их разграничение или разбивку между базами данных.

*Пришлите блоксхему, где и что будет располагаться. Опишите, в каких режимах будут работать сервера.* 

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

---
### Задание 3*

Выполните настройку выбранных методов шардинга из задания 2.

*Пришлите конфиг Docker и SQL скрипт с командами для базы данных*.
