## Задача 1

![Запуск контейнера](task1/running.png)
![Загрузка в репозиторий](task1/push.png)
![Страница в браузере](task1/browser.png)
[Ссылка на docker hub](https://hub.docker.com/repository/docker/rai68/custom-nginx/general)


## Задача 2

![Запуск контейнера с тегом ФИО](task2/1.png)
![Переименование](task2/2-3-4.png)


## Задача 3
![Запуск контейнера](task3/1.png)
![Стоп контейнер](task3/2.png)
При запуске docker контейнера основной процесс nginx имеет PID 1. Контейнер будет работать до тех пор, пока запущен этот процесс. Нажатие клавиш Ctrl-C отправляет сигнал SIGINT текущему (основному) процессу, он перестает работать, а вместе с ним происходит и остановка контейнера

![Install nano](task3/install_nano.png)
![Edit config](task3/edit-config.png)
![Edit config](task3/edit_config_nginx.png)
При запуске контейнера был сделан мапинг порта 8080 хостовой машины на порт 80 контейнера, затем в конфигурации nginx был изменен прослушиваемый порт с 80 на 81. Т.е. nginx стал работать на 81 порту, который не привязан к порту 8080 хостовой машины, а значит не доступен при обращении с нее к контейнеру.

Попробуем исправить проблемы с доступностью nginx

![Edit config](task3/11-1.png)
![Edit config v2](task3/edit_config_v2.png)
![Edit hostconfig](task3/edit_hostconfig.png)
![Stop container](task3/11_12.png)
Теперь все снова работает!