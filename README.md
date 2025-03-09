# Домашнее задание к занятию "`Задание по занятию "Docker. Часть 2"
`Климов Дмитрий`


### Задание 1
Напишите ответ в свободной форме, не больше одного абзаца текста.

Установите Docker Compose и опишите, для чего он нужен и как может улучшить лично вашу жизнь.

Docker Compose - это инструмент для определения и запуска многоконтейнерных Docker-приложений. Вместо того, чтобы вручную запускать каждый контейнер с множеством параметров, Compose позволяет описать всю конфигурацию приложения в одном YAML-файле. В моей личной жизни, это упрощает разработку и тестирование: я могу быстро развернуть сразу несколько взаимосвязанных сервисов (например, веб-сервер, базу данных и кэш) для локальной разработки, не тратя время на сложную настройку. Когда я заканчиваю работу над проектом, я могу легко остановить и удалить все контейнеры одной командой, сохраняя чистоту моей системы. Это значительно экономит время и снижает вероятность ошибок, делая процесс разработки более эффективным и приятным.

![Снимок экрана (511)](https://github.com/user-attachments/assets/c93ccb1d-2d0a-429b-bd14-58465d7d4f74)


### Задание 2
Выполните действия и приложите текст конфига на этом этапе.

Создайте файл docker-compose.yml и внесите туда первичные настройки:

version;
services;
volumes;
networks.
При выполнении задания используйте подсеть 10.5.0.0/16. Ваша подсеть должна называться: <ваши фамилия и инициалы>-my-netology-hw. Все приложения из последующих заданий должны находиться в этой конфигурации.

![Снимок экрана (512)](https://github.com/user-attachments/assets/8ab5bb42-2b2d-4bab-8729-05c2eabbef17)


### Задание 3
Выполните действия:

Создайте конфигурацию docker-compose для Prometheus с именем контейнера <ваши фамилия и инициалы>-netology-prometheus.
Добавьте необходимые тома с данными и конфигурацией (конфигурация лежит в репозитории в директории 6-04/prometheus ).
Обеспечьте внешний доступ к порту 9090 c докер-сервера.

![Снимок экрана (527)](https://github.com/user-attachments/assets/27ba64c7-c91e-4ead-a801-f9d07e352e0e)


![Снимок экрана (526)](https://github.com/user-attachments/assets/d4979e8c-b00f-4169-add9-e8afbcc2c1b3)

### Задание 4
Выполните действия:

Создайте конфигурацию docker-compose для Pushgateway с именем контейнера <ваши фамилия и инициалы>-netology-pushgateway.
Обеспечьте внешний доступ к порту 9091 c докер-сервера.

![Снимок экрана (528)](https://github.com/user-attachments/assets/964b4e16-0678-49ec-be80-f4573f12f3e6)

![Снимок экрана (529)](https://github.com/user-attachments/assets/72faa7dc-6518-4e95-8ba8-0c180de84d74)

![Снимок экрана (530)](https://github.com/user-attachments/assets/184045b9-694c-456e-a194-59fdf9d1ceaf)

### Задание 5
Выполните действия:

Создайте конфигурацию docker-compose для Grafana с именем контейнера <ваши фамилия и инициалы>-netology-grafana.
Добавьте необходимые тома с данными и конфигурацией (конфигурация лежит в репозитории в директории 6-04/grafana.
Добавьте переменную окружения с путем до файла с кастомными настройками (должен быть в томе), в самом файле пропишите логин=<ваши фамилия и инициалы> пароль=netology.
Обеспечьте внешний доступ к порту 3000 c порта 80 докер-сервера.


![Снимок экрана (531)](https://github.com/user-attachments/assets/504be6a9-d39c-4592-bfae-f70206ff0c7d)

![Снимок экрана (532)](https://github.com/user-attachments/assets/71d51afd-c851-4151-b643-a2566fe819c8)

![Снимок экрана (533)](https://github.com/user-attachments/assets/51fc35bb-512d-46d3-a40f-8f51bce09e5c)

![Снимок экрана (534)](https://github.com/user-attachments/assets/bb97f953-aa53-4e21-a836-fb8184254bad)


### Задание 6
Выполните действия.

Настройте поочередность запуска контейнеров.
Настройте режимы перезапуска для контейнеров.
Настройте использование контейнерами одной сети.
Запустите сценарий в detached режиме.


![Снимок экрана (535)](https://github.com/user-attachments/assets/bcf04164-e0ac-46f6-ab22-4d0e2c58c19a)

![Снимок экрана (536)](https://github.com/user-attachments/assets/68d4286b-73a8-4abd-8e8a-a9097b11a02f)

![Снимок экрана (537)](https://github.com/user-attachments/assets/a1aa4f84-8751-4077-9dda-7a227a8d3c1d)

Порядок запуска контейнеров:

klimovdg-netology-pushgateway
klimovdg-netology-prometheus
klimovdg-netology-grafana
Преимущества:

Управляемый порядок запуска: мы можем быть уверены, что контейнеры будут запускаться в правильном порядке, чтобы избежать проблем с зависимостью.
Автоматический перезапуск: если какой-либо из контейнеров упадет, он будет автоматически перезапущен, что обеспечит более высокую доступность.
Взаимодействие контейнеров: все контейнеры работают в одной сети, что позволяет им легко взаимодействовать друг с другом.
Эта реализация обеспечивает более надежную и управляемую среду для наших Prometheus, Pushgateway и Grafana.



### Задание 7
Выполните действия.

Выполните запрос в Pushgateway для помещения метрики <ваши фамилия и инициалы> со значением 5 в Prometheus: echo "<ваши фамилия и инициалы> 5" | curl --data-binary @- http://localhost:9091/metrics/job/netology.
Залогиньтесь в Grafana с помощью логина и пароля из предыдущего задания.
Cоздайте Data Source Prometheus (Home -> Connections -> Data sources -> Add data source -> Prometheus -> указать "Prometheus server URL = http://prometheus:9090" -> Save & Test).
Создайте график на основе добавленной в пункте 5 метрики (Build a dashboard -> Add visualization -> Prometheus -> Select metric -> Metric explorer -> <ваши фамилия и инициалы -> Apply.
В качестве решения приложите:

docker-compose.yml целиком;
скриншот команды docker ps после запуске docker-compose.yml;
скриншот графика, постоенного на основе вашей метрики.


![Снимок экрана (545)](https://github.com/user-attachments/assets/c9a8e23a-d203-4929-85ac-a9a9eebf90a4)

![Снимок экрана (546)](https://github.com/user-attachments/assets/c707cd13-b141-4a8c-bd30-7d29e60d652e)

![Снимок экрана (547)](https://github.com/user-attachments/assets/2782d9bb-7d9b-4862-b7fe-142f3d8beed2)

![Снимок экрана (544)](https://github.com/user-attachments/assets/559b6bc2-c249-4ca3-bf56-3c6636079ee3)

![Снимок экрана (543)](https://github.com/user-attachments/assets/89fdc88d-5426-4362-9ef3-56ee59810b08)

![Снимок экрана (542)](https://github.com/user-attachments/assets/d72fa0f2-3095-41d0-b680-94a44bdb6384)

![Снимок экрана (541)](https://github.com/user-attachments/assets/d248adf4-b51c-4d50-93e5-755f0922593e)




### Задание 8
Выполните действия:

Остановите и удалите все контейнеры одной командой.
В качестве решения приложите скриншот консоли с проделанными действиями.

![Снимок экрана (548)](https://github.com/user-attachments/assets/35258d9a-baf5-4e74-98cb-699d14ff399c)


