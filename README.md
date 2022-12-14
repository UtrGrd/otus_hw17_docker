# OTUS ДЗ №17. Docker. #
-----------------------------------------------------------------------
## Домашнее задание ##

1. Определите разницу между контейнером и образом. Вывод опишите в домашнем задании.
2. Ответьте на вопрос: Можно ли в контейнере собрать ядро?
3. Создайте свой кастомный образ nginx на базе alpine. После запуска nginx должен отдавать кастомную страницу (достаточно изменить дефолтную страницу nginx). Собранный образ необходимо запушить в docker hub и дать ссылку на ваш репозиторий.


## Результат ##

### 1. Определите разницу между контейнером и образом. Вывод опишите в домашнем задании. ###

Образ - это шаблон / компонент для сборки, открытый для чтения. На базе него создается контейнер.
Контейнер - абстракция над образом, открытая на чтение/запись. В ней происходит работа приложения.

### 2. Ответьте на вопрос: Можно ли в контейнере собрать ядро? ###

В конейнере собрать ядро можно, но с него нельзя загрузиться.

### 3. Создайте свой кастомный образ nginx на базе alpine. После запуска nginx должен отдавать кастомную страницу (достаточно изменить дефолтную страницу nginx). Собранный образ необходимо запушить в docker hub и дать ссылку на ваш репозиторий. ###

Ссылка на репозиторий в Docker hub:
https://hub.docker.com/repository/docker/kgndsn/nginx_otus

1. Устанавливаем и запускаем docker. 
2. Готовим [Dockerfile](https://github.com/UtrGrd/otus_hw17_docker/blob/main/Dockerfile) и [index.hmtl](https://github.com/UtrGrd/otus_hw17_docker/blob/main/index.html)
3. Собираем образ в текущей директории командой ```docker build -t kgndsn/nginx_otus:nginx_v1 .```
4. Запускаем новый образ на порту 1234 командой ```docker run -d -p 1234:80 kgndsn/nginx_otus:nginx_v1```
5. Логинимся на docker, командой ```docker login``` 
6. Push'им образ командой ```docker push kgndsn/nginx_otus:nginx_v1```
