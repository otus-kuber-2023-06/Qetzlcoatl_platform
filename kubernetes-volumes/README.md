1. Из предоставленных манифестов созданы StatefulSet и HeadlessService для MinIO. Изучена полученная структура кластера.
2. Кластер "очищен".
3. Из манифестов my-pv.yaml и my-pvc.yaml созданы, соответсвенно, PersistentVolume и PersistenVolumeClaim.
4. Из манифеста my-pod создан Pod, использующий ранее созданный PVC. Исследована связь между PVC и PV. В подключенный том записаны "контрольные данные". Pod удалён.
5. Из манифеста my-pod-2 создан новый Pod, использующий тот же PVC. Рассмотрено наличие тех же "контрольных данных", которые были записаны в том при работе с предыдущим Pod.