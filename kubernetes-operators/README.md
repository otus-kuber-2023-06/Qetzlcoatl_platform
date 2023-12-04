# kubernetes-operators

1. Создан CRD для создания ресурсов тиа  "БД MySQL" и установлен в default namespace
2. Создан написанный на Pyhton operator (и набор Jinja2 шаблонов к нему) для создания/удаления инстансов MySQL CRD, включающий резервное копирование СУБД при удалении и восстановление при создании (при наличии РК)
3. Создан docker-образ, запускающий данный оператор
4. Оператор установлен в кластер (default namespace)
5. Создан CR типа MySQL
6. Проверена работа оператора при создании, удалении и воссоздании данного CR

[olegus@talon ~/OTUS/Kubernetes/Github/Qetzlcoatl_platform/kubernetes-operators/]$ kubectl get jobs
NAME                         COMPLETIONS   DURATION   AGE
backup-mysql-instance-job    1/1           4s         2m27s
restore-mysql-instance-job   1/1           45s        108s
[olegus@talon ~/OTUS/Kubernetes/Github/Qetzlcoatl_platform/kubernetes-operators/]$ export MYSQLPOD=$(kubectl get pods -l app=mysql-instance -o jsonpath="{.items[*].metadata.name}")
[olegus@talon ~/OTUS/Kubernetes/Github/Qetzlcoatl_platform/kubernetes-operators/]$ kubectl exec -it $MYSQLPOD -- mysql -potuspassword -e "select * from test;" otus-database
mysql: [Warning] Using a password on the command line interface can be insecure.
+----+-------------+
| id | name        |
+----+-------------+
|  1 | some data   |
|  2 | some data-2 |
+----+-------------+
