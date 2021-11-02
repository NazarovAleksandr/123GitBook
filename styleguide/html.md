# 🌳 HTML

### Общие рекомендации.

Старайтесь использовать поменьше пустых и ненужных HTML-элементов. Например, разделители/подчёркивания можно создать использовав псевлоэлемент (`before`, `after`). Конечно, если с такими элементами не нужно взаимодействие, получить доступ к ним из JS не удастся

### Базовая часть разметки.

**2.2.1**

* Современный тип документа `<!DOCTYPE html>`
* Корневой элемент `<html>` с языком документа `lang`
* Метаинформация `<head>`
* Заголовок документа `<title>`
* Кодировка документа `<meta charset="utf-8">`. Кодировка символов на странице явно указана, чтобы обеспечить корректное отображение текста.
* Тело документа `<body>`

```
<!-- Хорошо -->
<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="utf-8">
    <title>Заголовок</title>
  </head>
  <body>Страница</body>
</html>

<!-- Плохо -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" 
"http://www.w3.org/TR/html4/strict.dtd">
<html>
  <title>Заголовок</title>
  Страница
</html>
```

### Форматирование тегов.

> Правила относятся как к HTML тегам, так и React-элементам.

**2.3.1** Вложенность тегов обозначается переносами и отступами.

**2.3.2** Каждый новый вложенный тег переносится на отдельную строку с отступом, кроме текстовых элементов.

**2.3.3** Двойные теги имеют открывающий и закрывающий теги.

**2.3.4** Одиночные теги не имеют закрывающий тег или слэш.

**2.3.5** Если тег имеет один атрибут, то текст внутри тега остётся на одной строке с тегом, в ином случае текст переносится на отдельную строку.

```
<!-- Хорошо -->
<div class="menu">
  <ul>
    <li>
      <a href="">Первый</a>
      <input type="text"/>
    </li>
    <li>
      <button type="button" className="button">
        Кнопка
      </button>
    </li>
  </ul>
</div>

<!-- Плохо -->
<div class="menu"><ul>
  <li><a href="">
    Первый
  </a></li>
  <input type="text"></input>
  <li><a href="">Второй
  </a></li>
  <button type="button" className="button">Кнопка</button>
</ul></div>
```

### Форматирование атрибутов.

> Под атрибутом стоит понимать HTML-атрибуты и пропсы, прокидываемые в React-элемент.

**2.4.1** Значения атрибутов записаны в двойных кавычках.

**2.4.2** Вложенные кавычки в значениях являются одинарными.

**2.4.3** Логические атрибуты записаны без значения. Также, если значение прокидываемой пропсы положительное, то значение не указывается. Такие атрибуты должны быть указаны последними.

**2.4.4** Если тег имеет более 3-х атрибутов, то каждый атрибут переносится на отдельную строку. Закрывающий литерал тега (`>`) также переносится.

```
<!-- Хорошо -->
<Button
  type="submit"
  color="primary"
  className={styles.button}
  onСlick="handleSubmit('menu')"
  disabled
>
  Сохранить
</Button>

<!-- Плохо -->
<Button type='submit'
  color='primary'
  className={styles.button}
  onСlick="handleSubmit("menu")"
  disabled="true">Сохранить</Button>
```

### Размеры замещаемых элементов.

**2.5.1** У изображений, видео и iframe указаны размеры. По возможности изображениям указываются действительные размеры, так как это улучшает производительность отрисовки страницы: при отрисовке страницы браузер будет оставлять нужное количество пространства ещё до загрузки самого изображения. Это позволяет избежать смещения раскладки страницы по мере загрузки изображений.

**2.5.2** В атрибутах нет единиц измерения.

```
<!-- Хорошо -->
<img src="logo.png" alt="logo" width="300" height="150">
<svg width="16" height="16" xmlns="http://www.w3.org/2000/svg"></svg>
<video src="source/video.mp4" width="400" height="400"></video>
<iframe src="https://maps.google.com" width="400" height="400"></iframe>

<!-- Плохо -->
<img src="logo.png" alt="" width="300px" height="150px">
<svg xmlns="http://www.w3.org/2000/svg"></svg>
<video src="source/video.mp4"></video>
<iframe src="https://maps.google.com"></iframe>
```

### Наименование классов.

**2.6.1** Классы именуются латиницей в `camelCase` т.к в связке с CSS Modules удобнее всего использовать именно такой стиль написания.

> Полная схема: `(NamespaceName/elementName)_modifierName-modifierValue`

```
<!-- Хорошо -->
<section className={`${styles.section} ${styles.section_visible}`}>
 <h3 className={styles.hidden}>Список пользователей</h3>
  <ul className={styles.list}>
    <li className={styles.item}>
      <span className={`${styles.itemName} ${styles.itemName_uppercase}`}>
        Иванов
      </span>
    </li>
    <li className={styles.item}>
      <span className={styles.itemName}>Петров</span>
    </li>
  </ul>
</section>
```

**2.6.2  **Значение модификатора отделяется от его имени одиночным нижним подчёркиванием `(_)`.

```
<div className={`${styles.itemName} ${styles.itemName_colored}`} />
```

**2.6.3 **Для отделения названия модификатора от его значения используется дефис `(-)`.

```
 <div className={`${styles.userList} ${styles['userList_sideLeft-visible']}`} />
```

**2.6.4** Имя класса корневого элемента в компоненте всегда `.root`.

**2.6.5 **Для глобальных классов используется те же правила именования, только название компонента в PascalCase.

```
<!-- App.modules.css / объявляем глобальный класс -->
:global(.userList) {}

<!-- ComponentA.modules.css / используем глобальный класс -->
.wrapper :global(.App_userList) {}
```

**2.6.6 **Дочерний элемент не участвует в схеме именования.

```
<!-- Хорошо -->
<div className="elementName">
  <p className="childName" />
</div>

<!-- Плохо -->
<div className="elementName">
  <p className="elementName_childName" />
</div>
```

**2.6.7** Если нужно взаимодействовать с элементом из JS по классу, создайте отдельный класс с пефиксом `js`. Это облегчит рефакторинг и позволит избежать неожиданных багов.

```
<button className={`${styles.button} ${styles.jsUpdateButtonPosition}`}/>
```
