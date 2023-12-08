# kubernetes-templating

1. При подготовке к выполнению дальнейших шагов в Kubernetes кластере в Yandex.Cloud был создан namespace ingress-nginx. В него из репозитория <https://kubernetes.github.io/ingress-nginx> был установлен шаблон ingress-nginx.
2. На следующем шаге был создан namespace cert-manager, в который из репо <https://charts.jetstack.io> был установлен шаблон cert-manager и созданы 2 issuer (staging и prod) использующих для выпуска сертификатов сервис Let's Encrypt.
3. Создан namespace chartmuseum, из репо <https://chartmuseum.github.io/charts> был установлен шаблон chartmuseum с использованием переменных из файла values.yaml.
4. Создан namespace harbor, из репо <https://github.com/goharbor/harbor-helm> был установлен шаблон harbor с использованием переменных из файла values.yaml для этого проекта.
5. Создан локальный шаблон hipster-shop и установлен в namespace hipster-shop.
6. Создан другой локальный шаблон frontend, в который из hipster-shop вынесен микросервис frontend . Он модифицирован на использование переменных из values.yaml.
7. hipster-shop модифицирован на использование микросервиса frontend в качестве внешней зависимости.
8. Задания со * и необязательные задания разобраны теоретически и не выполнялись практически ввиду нехватки времени.
