# Микросервисная архитектура и контейнеризация
![](logo.png)
#### Факультет Data Engineering
___
[Курсовой проект](https://github.com/TolstikovIgor/containerization/tree/main/lesson8)
____
#### Урок 1. Микросервисы и контейнеры
* Монолиты
  * Одно приложение
  * Всё взаимодействие внутри
  * Легко накапливают спагетти-код
* Микросервисы
  * Хорошо эксплуатируемые и тестируемые
  * Низкое зацепление
  * Независимый деплой
  * Построены вокруг бизнес функционала
  * Пишутся небольшой командой
* Контейнеры и образы
  * Container
  * Images
  * Registry
* Docker не про контейнеры

#### [Урок 2. Docker](https://github.com/TolstikovIgor/containerization/tree/main/lesson2)
1. Запуск контейнеров
2. Создание образов
3. Dockerfile
   * Код приложения
   * Зависимости приложения
   * Операционная система
4. Запуск мультисервисных окружений (docker-compose)
5. Оркестратор контейнеров

#### [Урок 3. Введение в Kubernetes](https://github.com/TolstikovIgor/containerization/tree/main/lesson3)
* Kubernetes — это оркестратор контейнеров
* Главные принципы Kubernetes
  * Immutable
  * Declarative
  * Self-healing
  * Decoupling
* Как оно работает
  * Kubernetes Workflow
  * Pod
  * ReplicaSet
  * Deployment

#### [Урок 4. Хранение данных и ресурсы](https://github.com/TolstikovIgor/containerization/tree/main/lesson4)
* Ресурсы контейнеров
  * Limits
  * Requests
* Хранение конфигураций
  * ConfigMap
  * Secret
* Персистентность
  * Persistent Volume
  * Persistent Volume Claim
  * PV Provisioners

#### [Урок 5. Сетевые абстракции Kubernetes](https://github.com/TolstikovIgor/containerization/tree/main/lesson5)
1. Service
2. Проверки доступности
   * Liveness Probe
   * Readiness Probe
4. Ingress
5. Сетевые плагины
   * Обеспечивает связь между подами в кластере
   * Раздает IP-адреса подам
   * Реализует шифрование трафика*
   * Управляет Network Policies*
   * Популярные CNI плагины

#### Урок 6. Устройство кластера
1. Etcd
    * Хранит всю информацию о кластере
    * Etcdctl — утилита управления кластером ETCD
    * Требует быстрых дисков
2. Kube-API-server
    * Центральный компонент Kubernetes
    * Единственный, кто общается с Etcd
    * Работает по REST API
    * Authentication and authorization
3. Kube-controller-manager
    * Набор контроллеров
       * Node controller
       * Replication controller
       * Endpoints controller
       * И другие…
    * GarbageCollector — «сборщик мусора»
4. Kube-scheduler
    * Назначает PODы на ноды, учитывая:
       * QoS
       * Aﬃnity / anti-aﬃnity
       * Requested resources
5. Kubelet
   * Работает на каждой ноде
   * Единственный компонент, работающий не в Docker
   * Отдает команды Docker daemon
   * Создает PODы
6. Kube-proxy
   * Смотрит в Kube-API
   * Стоит на всех серверах
   * Управляет сетевыми правилами на нодах
   * Фактически реализует Service (ipvs и iptables)
7. HA кластер

#### [Урок 7. Продвинутые абстракции](https://github.com/TolstikovIgor/containerization/tree/main/lesson7)
1. DaemonSet
   * Запускает поды на всех нодах кластера
   * При добавлении ноды – добавляет под
   * При удалении ноды GC удаляет под
   * Описание практически полностью соответствует Deployment
2. StatefulSet
   * Позволяет запускать группу подов (как Deployment)
   * PVC template
   * Используется для запуска приложений с сохранением состояния
3. Job
   * Создает под для выполнения задачи
   * Перезапускает поды
4. CronJob
   * Создает Job по расписанию
   * Важные параметры
5. Horizontal Pod Autoscaler

#### [Урок 8. Деплой тестового приложения в кластер, CI/CD](https://github.com/TolstikovIgor/containerization/tree/main/lesson8)
1. CI/CD
   * Continuous Integration
   * Continuous Delivery
   * Continuous Deployment
2. Gitlab
   * Хранение и работа с кодом
   * Хранение артефактов
   * Пайплайны
3. Автоматизированная сборка
4. Тестирование
5. Деплой в Kubernetes


[сертификат](https://gb.ru/go/D-35xc)
