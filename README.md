## ДЗ 1
Для выполнения домашней работы создан Dockerfile, в
котором был описан образ:
* Запускающий web-сервер на порту 8000 (можно использовать любой
способ)
* Отдающий содержимое директории  /app  внутри контейнера (например,
если в директории  /app  лежит файл  homework.html , то при запуске
контейнера данный файл должен быть доступен по URL 
http://localhost:8000/homework.html )
* Работающий с UID 1001

## ДЗ 2
### Почему ReplicaSet не обновляет запущенные поды
Replicaset не следит за соответсвие подов шаблону, только за количество запущенных реплик

### Написать ReplicaSet и Deployment для frontend и payment
Созданы yaml файлы с описанием

### Написать blue-green и reverse обновление с параметрами maxUnavailable maxSurge
Созданы yaml файлы с описанием, bg - paymentservice-deployment-bg, reverse - paymentservice-deployment-reverse

### Probes
Добавлен в frontend-deployment

### DaemonSet Node-Exporter
Создан yaml node-exporter-daemonset

### DaemonSet на master
Добавлен параметр tolerations в node-exporter-daemonset