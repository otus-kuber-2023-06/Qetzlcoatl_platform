# Qetzlcoatl_platform
Qetzlcoatl Platform repository

В папке kubernetes-intro созданы
1. папка web в которой хранятся пререквизиты для создания Docker образа с Nginx в среде Ubuntu, слушающий на порту 8000 и отдающий содержимое папки /app в образе.
2. yaml манифест создания pod-а из данного образа с использованием init контейнера и emptyDir хранилища
