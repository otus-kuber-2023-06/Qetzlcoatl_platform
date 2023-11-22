# kubernetes-security

1. В рамках задания task01 в default namespace созданы 2 ServiceAccount-а - bob, с максимальными правами в рамках кластера (системная роль cluster-admin), и dave, не имеющи никаких прав в кластере (никакая роль не назначена, т.е. по-умолчанию никаких прав нет).
2. В рамках задания task02 создан namespace (prometheus), все SA которого имеют read-only права на все pod-ы в кластере, независимо от их namespace, а также один SA в этом namespace.
3. В рамках задания task03 создан namespace (dev), в котором один SA (jane) получил системную роль admin для данного namespace, а другой (ken) системную роль view так же только в рамках данного namespace.
