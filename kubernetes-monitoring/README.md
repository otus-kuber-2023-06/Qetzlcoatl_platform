# kubernetes-security

1. В namespace default кластера установлен Prometheus.
2. Подготовлен Docker-образ nginx с работающей страницей /basic_status .
3. В namespace default кластера установлен deployment с 3 репликами nginx + nginx-exporter, сервис для него, настроены serviceaccount + RBAC для Prometheus, servicemonitor и prometheus для мониторинга этого деплоя.

Пример графика мониторинга значения nginx_http_requests_total для созданного нами nginx.

![nginx_http_requests_total picture](./totalRequestsGraph.jpg?raw=true)

PS. "Уровни сложности" - слишком простая задача для олдфагов. Это всё уровни сложности из оригинальной PC версии Wolfenstein 3D.
