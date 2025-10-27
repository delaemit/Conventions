## Шаблон для создания BUG-REPORT'a

- укажите префикс репозитория в заголовке (title): `FE | BE`
  
- добавьте [исполнителя](./team.md) по-умолчанию (assignees):
```
egnvk
```

- скопируйте код в корень репозитория `.github/ISSUE_TEMPLATE/1-bug_report.yaml`
  
```yml
name: Баг Репорт
description: Отчет об ошибке
assignees: egnvk
title: "[Bug]: BE: "
type: bug
body:
  - type: markdown
    attributes:
      value: |
        Краткое описание проблемы.
  - type: textarea
    id: what-happened
    attributes:
      label: 📝 Что случилось?
      description: |
        Шаги для воспроизведения и ожидаемый результат.
        **Приложите дополнительные материалы:** скриншоты, ссылку на видео, запросы из браузера, 
        тексты ошибок из консоли или логов.
      placeholder: | 
        Что бы воиспроизвести баг нужно: 
        Открыть главную страницу, ввести данные в поле Имя, нажать кнопку Отправить. 
        Кнопка Отправить не активна, а должна нажиматься и отправлять форму.
      value: Случился баг!
  - type: textarea
    id: fix
    attributes:
      label: 🚧 Как исправить?
      description: |
        Комментарии технического специалиста по исправлению данного бага, 
        включающий описание компонентов, апи, архитектуру приложения, структуру базы данных...
      value: Надо дебажить!
  - type: textarea
    id: environment
    attributes:
      label: 🖱️ Окружение
      description: Где вы поймали жука?
      value: |
        Браузер:
        Устройство: ПК / Мобилка
  - type: checkboxes
    id: terms
    attributes:
      label: ✅ Версия приложения
      options:
        - label: дев-стенд
        - label: продакшн
  - type: dropdown
    id: version
    attributes:
      label: 📌 Приоритет
      description: На сколько серьёзный баг для основного бизнес процесса?
      options:
        - 🚑 Критический
        - 🚨 Высокий
        - 🔥 Средний
        - 🤬 Низкий
      default: 0
```
