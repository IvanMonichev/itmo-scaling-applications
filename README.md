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