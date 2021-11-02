# Главная страница

## v.1.6 - 2021-08-05

### Added

* Добавлен раздел с [тестированием](styleguide/testing.md). Новое правило - **7.1.1**
* Добавлены правила именования [React пропсов](styleguide/react.md#obshie-rekomendacii). Правила **6.1.8** и **6.1.9**

## v.1.5 - 2021-08-04

### Added

* Добавлены [правила именования классов](styleguide/html.md#naimenovanie-klassov). Правила **2.6.2 - 2.6.6**

## v1.4 - 2021-07-25

### Changes

* Заменён набор правил `stylelint-config-idiomatic-order` на `stylelint-config-rational-order` т.к. этот набор больше подходит. Конфиг отвечает за [порядок свойств](styleguide/css-sass.md#poryadok-svoistv).

### Added

* Плагин `stylelint-at-rule-no-children`. [Раздел,](styleguide/css-sass.md#struktura-obyavleniya) правило **3.2.11**, которое запрещает вложенность ("нестинг") внутри операторов `@at-rule`.
* Плагин `stylelint-group-selector`. Находит селекторы, которые можно сгруппировать (имеют одинаковый набор свойств и значений). [Раздел](styleguide/css-sass.md#struktura-obyavleniya), правило **3.2.13**
* Описаны правила для stylelint, которые отвечают за порядок объявления свойств в селекторе. [Раздел](styleguide/css-sass.md#struktura-obyavleniya), правило **3.2.9**. Раньше на это не было линтинга, но информация присутствовала в стайлгайде.
* Сброшены правила stylelint, которые конфликтуют с правилами для SASS.
* Для SASS добавлены отдельные правила, которые в основном отвечают за форматирование.
* В [разделе](styleguide/css-sass.md#specifichnost-stilei-kaskadirovanie) новое правило **3.4.4**, которое говорит о том, что не следует избыточно вкладывать селекторы через `&`
