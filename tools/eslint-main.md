# Общая информация

## Запуск проверок.

В корне проекта в `.package.json` описаны скрипты.

Описание флагов:

`-ignore-path`: при проверке игнорировать следующий путь

`-cache`: проверяет только изменённые файлы. Кэши проверок хранятся в `.eslintcache` и `.stylelintcache`

**Проверяет на наличие ошибок в коде через Eslint:**

> `"eslint": "eslint --ignore-path .eslintignore --cache --ext .js,.jsx,.ts,.tsx ."`

**Проверяет на наличие и исправляет возможные ошибки через Eslint:**

> `"eslint:fix": "eslint --ignore-path .eslintignore --cache --fix \"**/*.{js,jsx,ts,tsx}\""`

**Проверяет на наличие ошибок в коде через Stylelint:**

> `"stylelint": "stylelint --ignore-path .stylelintignore --cache \"**/*.{css,scss,sass}\""`

**Проверяет на наличие и исправляет возможные ошибки через Stylelint:**

> `"stylelint:fix": "stylelint --ignore-path .stylelintignore --cache --fix \"**/*.{css,scss,sass}\""`

**Форматирует код через Prettier:**

> `"prettier": "prettier --write \"**/*.{js,jsx,ts,tsx,css,scss,sass}\""`

**Проверяет на наличие ошибок через Eslint и Stylelint**

> `"lint": "yarn stylelint && yarn eslint"`

**Исправляет возможные ошибки через Eslint и Stylelint, форматирует код через Prettier**

> `"lint:fix": "yarn eslint:fix && yarn stylelint:fix && prettier"`

## [`Lint-staged`](https://github.com/okonet/lint-staged) в связке с [`Husky`](https://github.com/typicode/husky)

**Husky** позволяет задействовать хуки Git. Это означает, что у вас появляется возможность выполнять некие действия перед выполнением коммита или перед отправкой кода репозиторий.

**Lint-staged** - позволяет проверять с помощью линтера индексированные файлы, что помогает предотвратить отправку в репозиторий кода с ошибками.

Конфиг для **Lint-staged** можно найти в `.package.json`. Запускаем по очереди команды для проверки на ошибки, форматирование кода. Если на каком-либо этапе выполения код падает с ошибкой, то ваш коммит не пройдёт дальше.

```
"lint-staged": {
    "*.{js,jsx,ts,tsx}": [
      "yarn eslint"
    ],
    "*.{css,scss,sass}": [
      "yarn stylelint"
    ],
    "*.{js,jsx,ts,tsx,css,scss,sass}": [
      "yarn prettier"
    ]
  }
```

## Настройка редактора.

Для полноценной работы с линтерами необходимо установить расширения для IDE, без них вы не увидите подсвечивание ошибок в коде.

> [Список IDE и ссылки на расширения для ESLint](https://eslint.org/docs/user-guide/integrations)
>
> [Список IDE и ссылки на расширения для Stylelint](https://stylelint.io/user-guide/integrations/editor)

Для удобства можно настроить редактор так, чтобы линтер автоматически исправлял ошибки в файле после его сохранения (удобно для форматирования стилей через Stylelint).

Ещё одним вариантом является установка хот-кея для автоматического исправления.

> [Как установить хот-кей для исправления ошибок через ESLint](https://medium.com/@netczuk/even-faster-code-formatting-using-eslint-22b80d061461)
>
> [Как установить хот-кей для исправления ошибок через StyleLint (Webstorm)](https://www.jetbrains.com/help/webstorm/using-stylelint-code-quality-tool.html)

##
