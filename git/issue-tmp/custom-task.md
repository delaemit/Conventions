## Шаблон для создания любой задачи

- укажите префикс репозитория в заголовке (title): `FE | BE`
  
- добавьте [исполнителя](./team.md) по-умолчанию (assignees):
```
egnvk
```

- скопируйте код в корень репозитория `.github/ISSUE_TEMPLATE/3-custom.yaml`

```yml
name: Просто Задача
description: Любая задача
assignees: egnvk
title: "BE: "
type: task
body:
  - type: textarea
    id: task
    attributes:
      label: Задача
      placeholder: TODO
    validations:
      required: true
```
