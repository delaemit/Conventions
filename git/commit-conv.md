## Commit Convention
Это соглашение о том, как нужно писать сообщения commit’ов. Оно описывает набор правил для создания понятной истории commit’ов, 
а также позволяет проще разрабатывать инструменты автоматизации, основанные на истории commit’ов.

Сообщения commit’ов должны быть следующей структуры:
```
[optional task number]: <type>[optional scope]: <optional icon> <description>

[optional body]

[optional footer]
```

Commit’ы могут содержать следующие структурные элементы для сообщений:

- **fix**: commit типа `fix` исправляет ошибку (bug) в вашем коде.
- **feat**: commit типа `feat` добавляет новую функцию (feature) в ваш код.
**BREAKING CHANGE:** commit, который содержит текст `BREAKING CHANGE:` в начале своего не обязательного тела сообщения (body) или в подвале (footer), добавляет изменения, нарушающие обратную совместимость вашего API.
BREAKING CHANGE может быть частью commit’а любого типа.

Commit’ы с типами, которые отличаются от `fix:` и `feat:`, также разрешены.
Например, [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional) (основанный на The Angular convention) рекомендует: `chore:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, и другие.

### Типы
* `feat` :sparkles: `:sparkles:` Commits, that adds or remove a new feature
* `fix` :bug: `:bug:` Commits, that fixes a bug
* `refactor` :recycle: `:recycle:` Commits, that rewrite/restructure your code, however does not change any API behaviour
* `perf` :zap: `:zap:` Commits that improve performance
* `style` :lipstick: `:lipstick:` Commits, that reformat code and do not affect the meaning (white-space, formatting, missing semi-colons, etc)
* `test` :white_check_mark: `:white_check_mark:` Commits, that add missing tests or correcting existing tests
* `docs` :memo: `:memo:` Commits, that affect documentation only
* `build` :construction_worker: `:construction_worker:` Commits, that affect build components like build tool, ci pipeline, dependencies, project version, ...
* `ops` :hammer: `:hammer:` Commits, that affect operational components like infrastructure, deployment, backup, recovery, ...
* `chore` :construction: `:construction:` Miscellaneous commits e.g. modifying `.gitignore`, Work in progress., ...
* `revert` :rewind: `:rewind:` Revert

### Иконки
https://gitmoji.dev/

### Примеры
- Первый commit в ветке:
```  
123: initial commit
```
  
- Сообщение commit’а без тела:
```  
123: docs: correct spelling of CHANGELOG
```

- Сообщение commit’а с иконкой:
  
`"`123: :memo: docs: correct spelling of CHANGELOG`"`
```  
123: :memo: docs: correct spelling of CHANGELOG
```



- Сообщение commit’а с указанием контекста (scope):

```
123: feat(api): add polish language
```

- Сообщение commit’а, исправляющего ошибку (fix) с телом:
  
```
fix: correct minor typos in code

see the issue for details on the typos fixed

closes issue #12
```

- Сообщение commit’a с не обязательным !, для того, чтобы привлечь внимание к изменениям, нарушающим обратную совместимость:
  
```
chore!: drop Node 6 from testing matrix

BREAKING CHANGE: dropping Node 6 which hits end of life in April
```

### Инструменты
[Commit lint](https://commitlint.js.org/reference/cli)

[Commit lint use promt](https://commitlint.js.org/guides/use-prompt)

