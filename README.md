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

## ДЗ 3

### Task01
Последовательное применение 01_*.yaml 02_*.yaml и т.д. создает ServiceAccount bob с правами cluster-admin и ServiceAccount dave без прав доступа к кластеру

### Task02
Последовательное применение 01_*.yaml 02_*.yaml и т.д. создает Namespace prometheus, ServiceAccount carol в этом Namespace, Role cluster-pod-reader с правами на get, list, watch для всех Pods и связывает эту роль со всеми ServiceAccounts в Namespace prometheus

### Task03
Последовательное применение 01_*.yaml 02_*.yaml и т.д. 
создает Namespace dev, ServiceAccount jane, дает jane роль admin в рамках Namespace dev, SerivceAccount ken, дает ken роль view в рамках Namespace dev


## ДЗ 4
Создан Statefulset minio
Создан Headless-service
Создан Secret
Манифест minio изменен для использования секретов из Secret

## ДЗ 5
Добавление проверок Pod
Создание объекта Deployment
Добавление сервисов в кластер (ClusterIP)
Включение режима балансировки IPVS
Установка MetalLB в Layer2-режиме
Добавление сервиса LoadBalancer
Установка Ingress-контроллера и прокси ingress-nginx
Создание правил Ingress

Дополнительные задания:
Создан LoadBalancer для доступа к CoreDNS снаружи кластера
Добавлен доступ к kubernetes-dashboard через Ingress
Реализовано канареечное развертывание с помощью ingress-nginx

## ДЗ 6
Установка из Helm charts: cert-manager, chartmuseum, harbor
Использование Jsonnet и Kustomize

## ДЗ 7
prometheus-operator установлен из Helm чарта
Создан кастомный образ Nginx, deployment, service, servicemonitor