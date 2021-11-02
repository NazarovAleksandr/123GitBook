# 🧑‍🦽Тестирование

### Общие рекомендации.

**7.1.1** Для удобного поиска узлов DOM дерева в тестах, необходимо нужному элементу присвоить `data-*` атрибут: `data-testid`. Значение (название) атрибута должно быть записано в `PascalCase` и указывать на название компонента и элемента. Для разделения слов в именах используется (`_`).

> ComponentName\_componentElement

```
// ComponentA.jsx
<div className="root">
  <h1 className="header" data-testid="ComponentA_header">...</h1>
  <p className="paragraphOld" data-testid="ComponentA_paragraph_old">...</p>
  <p className="paragraphNew" data-testid="ComponentA_paragraph_new">...</p>
</div>
```
