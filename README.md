# Scaling Applications

## Содержимое registry
![01](images/01.jpg)

## Authenticating with the Registry
![alt text](images/02.jpg)
![alt text](images/03.jpg)
![alt text](images/04.jpg)

## Docker Orchestration Hands-on Lab
![alt text](images/05.png)
![alt text](images/06.png)
![alt text](images/07.png)
![alt text](images/08.png)
![alt text](images/09.png)
![alt text](images/10.png)

> Вопрос: восстановилась ли работа запущенного сервиса на этом узле?

Ответ: нет. После перевода узла из состояния Drain обратно в Active Docker Swarm не переносит задачи сервиса обратно автоматически.

> Что необходимо сделать, чтобы снова запустить сервис на этом узле?

Нужно инициировать перераспределение задач сервиса, или изменить количество реплик.

## Swarm stack introduction
![alt text](images/11.png)
![alt text](images/12.png)
![alt text](images/13.png)

> Как конфигурируется количество нодов в стэке?

Количество экземпляров сервисов в Docker Swarm-стэке задаётся в файле docker-stack.yml с помощью параметра deploy.replicas. Параметр определяет число реплик сервиса, которые планировщик Swarm автоматически распределяет по узлам кластера.

> Как организуется проверка жизнеспособности сервисов?

Контроль работоспособности осуществляется средствами Docker Swarm, который отслеживает состояние задач и автоматически перезапускает контейнеры в случае их отказа, поддерживая заданное количество реплик сервисов.

Docker Swarm поддерживает механизм healthcheck, который может быть описан в docker-stack.yml, например:

```yml
healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost"]
  interval: 30s
  timeout: 10s
  retries: 3
```