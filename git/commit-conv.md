## Commit Convention
Это соглашение о том, как нужно писать сообщения commit’ов. Оно описывает набор правил для создания понятной истории commit’ов, 
а также позволяет проще разрабатывать инструменты автоматизации, основанные на истории commit’ов.

Сообщения commit’ов должны быть следующей структуры:
```
<icon> [номер задачи или название ветки]: <опционально: тип>(опционально: scope): <описание>

[опционально: тело коммита]

[опционально: footer]
```

**Обязательно указывать номер задачи или название ветки и тип коммита (иконкой или текстом)!** 
Это нужно, чтобы в истории гита (`git log`) можно было легко понять куда откатится(`git reset --hard`) при нестабильной работе релизов на проде.

<br>
<br>

Коммиты могут содержать следующие структурные элементы для сообщений:

- **fix**: коммит типа `fix` исправляет ошибку (bug) в вашем коде.
- **feat**: коммит типа `feat` добавляет новую функцию (feature) в ваш код.
- **BREAKING CHANGE:** коммит, который содержит `!` или текст `BREAKING CHANGE:` в начале своего описания или не обязательного тела сообщения (body) или в подвале (footer), добавляет изменения, нарушающие обратную совместимость вашего API.
BREAKING CHANGE может быть частью commit’а любого типа.

Коммиты с типами, которые отличаются от `fix:` и `feat:`, также разрешены.
Например, [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional) (основанный на The Angular convention) рекомендует: `chore:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, и другие.

<br>
<br>

### Типы
* :tada: `initial commit` Это пустой коммит, создаётся сразу после, создания ветки под новый функционал.
* :tada: `инициализация` 
* ```
  :tada: initial commit
  ```
* `feat` :sparkles: `:sparkles:` Коммит с новым функционалом(фичей).
* `fix` :bug: `:bug:`  Коммит, исправляющий ошибку(баг).
* `refactor` :recycle: `:recycle:` Commits, that rewrite/restructure your code, however does not change any API behaviour
* `perf` :zap: `:zap:` Commits that improve performance
* `style` :lipstick: `:lipstick:` Commits, that reformat code and do not affect the meaning (white-space, formatting, missing semi-colons, etc)
* `test` :white_check_mark: `:white_check_mark:` Commits, that add missing tests or correcting existing tests
* `docs` :memo: `:memo:` Commits, that affect documentation only
* `build` :construction_worker: `:construction_worker:` Commits, that affect build components like build tool, ci pipeline, dependencies, project version, ...
* `ops` :hammer: `:hammer:` Commits, that affect operational components like infrastructure, deployment, backup, recovery, ...
* `debug` :test_tube: `:test_tube:` Коммит, с помощью, которого происходит дебагинг (тестирование) приложения, добавление логов, временное отключение какого-то функционала ...  
* `chore` :construction: `:construction:` Miscellaneous commits e.g. modifying `.gitignore`, Work in progress., ...
* `revert` :rewind: `:rewind:` Revert. Откат изменений.

### Иконки
https://gitmoji.dev/

### Примеры

- Сообщение коммита о новом функционале. Допустимы все три варианта, главное, чтобы было понятно - тип коммита и к какой теме (задаче) они относятся:
```  
:sparkles: feature/123: feat: валидация емаила при регистрации

:sparkles: feature/123: валидация емаила при регистрации

:sparkles: 123: валидация емаила при регистрации
 
```

- Сообщение коммита о новом функционале и инициализации ветки (**первый**):

```
:sparkles: 123: инициализация; валидация емаила при регистрации
  
:sparkles: feature/123: init commit; sign up email validation 
```
  
- Коммит без тела, без указания ветки и иконки, только тип изменения и сообщение:
```  
docs: correct spelling of CHANGELOG
```

- Сообщение коммита с иконкой:
  
`"`:memo: docs: correct spelling of CHANGELOG`"`
```  
:memo: docs: correct spelling of CHANGELOG
```



- Сообщение коммита с указанием ветки, типа и контекста (scope):

```
feature/123: feat(api): add chinese language
```

- Сообщение коммита, исправляющего ошибку (fix) с телом и иконкой:
  
```
:bug: fix: correct minor typos in code

see the issue for details on the typos fixed

closes issue #12
```

- Сообщение breaking change commit’a с `!`, для того, чтобы привлечь внимание к изменениям, нарушающим обратную совместимость:
  
```
chore!: drop Node 6 from testing matrix

BREAKING CHANGE: dropping Node 6 which hits end of life in April
```

>[!CAUTION]
>В ветку `main` коммитить запрещено, только через [PR](./pr-conv.md) !

### Инструменты
[Commit lint](https://commitlint.js.org/reference/cli)

[Commit lint use promt](https://commitlint.js.org/guides/use-prompt)

