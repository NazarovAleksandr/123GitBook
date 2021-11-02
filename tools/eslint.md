---
description: https://eslint.org/
---

# Eslint

Утилита, которая может анализировать и подсвечивать синтаксические ошибки, неточности форматирования и баги. Содержит около [300](https://eslint.org/docs/rules/) правил, по которым проверяет код. Автоматическое исправление поддерживают около 100 правил. Список подключенных плагинов, правил, конфигов и т.д. можно найти в `.eslintrc`

> `- extends`: конфиги, которые предоставляют предварительно настроенные правила (наборы правил)
>
> `- plugins`: правила, написанные с использованием парсера. Расширяют и дополняют основные правила **ESlint**

Для разных расширений файлов можно задать индивидульные настройки через `overrides`.

`.eslintignore` - файл содержит пути до файлов/папок, которые нужно игнорировать при проверке.

#### Поддерживаемые правила для `.js, .jsx`:

За основу взят конфиг [`Airbnb`](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb), который включает в себя:

> [`eslint-plugin-import`](https://github.com/benmosher/eslint-plugin-import): набор правил для поддержки синтаксиса импорта / экспорта ES2015 + (ES6 +) и предотвращения неправильного написания путей к файлам и имен импорта.
>
> [`eslint-plugin-react`](https://github.com/yannickcr/eslint-plugin-react): набор правил для проверки React компонентов
>
> [`eslint-plugin-react-hooks`](https://github.com/facebook/react/tree/master/packages/eslint-plugin-react-hooks): набор правил для React хуков
>
> [`eslint-plugin-jsx-a11y`](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y): набор правил для проверки элементов на доступность (accessibility)
>
> Парсер [`@babel/eslint-parser`](https://github.com/babel/babel-eslint): парсер, который позволяет ESLint работать с исходным кодом, преобразованным через Babel.

#### Поддерживаемые правила для `.ts, .tsx`:

> Плагин [`@typescript-eslint`](https://github.com/typescript-eslint/typescript-eslint) - расширяет возможности ESLint новыми правилами для TS
>
> Конфиг `@typescript-eslint/recommended`: рекомендованные правила для TS.
>
> Конфиг `@typescript-eslint/recommended-requiring-type-checking`: правила для проверки типов.
>
> Конфиг [`AirbnbTypescript`](https://github.com/iamturns/eslint-config-airbnb-typescript), который включает в себя Airbnb конфиг + правила для TS
>
> Парсер `@typescript-eslint/parser`: парсер TS, заменяет парсер ESLint.
>
> Конфиг находится в `.tsconfig.json`.
