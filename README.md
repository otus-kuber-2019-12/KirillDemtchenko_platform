# KirillDemtchenko_platform
KirillDemtchenko Platform repository

kubernetes-intro:
* Установил minikube и kind на рабочий компьютер.  
* Проверил, что в кластере восстанавливаются ноды после удаления: core-dns - как ReplicaSet, остальные kube-apiserver скорее всего контролируются системными процессами - но это не очевидно в отличии от core-dns.
* Создал Dockerfile для http сервера - на python http.server.
* Создал манифест web-pod.yaml.
* С помощью kubectl port-forward --address 0.0.0.0 pod/web 8000:8000 проверил работоспособность.
* Скопировал репозиторий hipster shop, собрал/запушил образ frontend
* Запустил под frontend - добавил необходимые переменные в env для запуска

kubernetes-controllers
* Создал поды с помощью ReplicaSet
* Попробовал изменить версию приложения, применяя новый манифест
* Попробовал изменить версию, удаляя поды и применяя манифест
* Изменений не произошло, потому что ReplicaSet не управляет изменениями. Что бы отслежививать изменения в репликаСета необходим Deployment как контроллер контроллеров.
* Создал RepliceSet и Deployment для сервиса paymentservice
* Попробовал накатить/откатить изменения с помощью Deployment
* Разобрался как с помощью Probe остлеживать корректность работы подов.

kubernetes-security

