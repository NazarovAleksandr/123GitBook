---
description: https://stylelint.io/
---

# Stylelint

Инструмент для линтинга стилей, который не только отлавливает ошибки, но и помогает соблюдать соглашения по стилю кода и применяемым практикам. Список подключенных плагинов, правил, конфигов и т.д. можно найти в `.stylelintrc`

> `- extends`: конфиги, которые предоставляют предварительно настроенные правила (наборы правил)
>
> `- plugins`: правила или набор правил, написанные разработчиками со всего мира. Расширяют и дополняют основные правила **Stylelint**

`.eslintignore` - файл содержит пути до файлов/папок, которые нужно игнорировать при проверке.

#### Поддерживаемые правила для `.css, .scss, .sass`:

> Плагин [`stylelint-order`](https://github.com/hudochenkov/stylelint-order) - расширяет правилами для управления порядком css свойств.
>
> Плагин [`stylelint-scss`](https://github.com/kristerkari/stylelint-scss) - расширяет правилами для управления SCSS синтаксисом.
>
> Плагин [`stylelint-group-selectors`](https://github.com/ssivanatarajan/stylelint-group-selectors) - находит селекторы, которые можно сгруппировать (имеют одинаковый набор свойств и значений).
>
> Плагин [`stylelint-at-rule-no-children`](https://github.com/adityavm/stylelint-at-rule-no-children) - правило, которое запрещает вложенность ("нестинг") внутри операторов @at-rule.
>
> Конфиг [`stylelint-config-rational-order`](https://github.com/constverum/stylelint-config-rational-order) - набор правил, которые регулируют порядок свойств на основе логической связи.
>
> Конфиг [`stylelint-config-htmlacademy`](https://github.com/htmlacademy/stylelint-config-htmlacademy) - зарекомендовавший себя набор правил от [HTML Academy](https://htmlacademy.ru)
