# ⚡️ React

### Общие рекомендации.

**6.1.1** Один файл - один React компонент.

**6.1.2** Всегда используйте `JSX` синтаксис.

**6.1.3** Название компонента и файла в `PascalCase`.

**6.1.4** Для экземпляров компонента название в `camelCase`.

```
// Плохо
import reservationCard from './ReservationCard';

// Хорошо
import ReservationCard from './ReservationCard';

// Плохо
const ReservationItem = <ReservationCard />;

// Хорошо
const reservationItem = <ReservationCard />;
```

**6.1.5** Именование компонента высшего порядка: Используйте сочетание имени компонента высшего порядка и имени переданного в него компонента как свойство displayName сгенерированного компонента. Например, из компонента высшего порядка withFoo(), которому передан компонент Bar, должен получаться компонент с displayName равным withFoo(Bar).

```
// Плохо
export default function withFoo(WrappedComponent) {
  return function WithFoo(props) {
    return <WrappedComponent {...props} foo />;
  }
}

// Хорошо
export default function withFoo(WrappedComponent) {
  function WithFoo(props) {
    return <WrappedComponent {...props} foo />;
  }

  const wrappedComponentName = WrappedComponent.displayName
    || WrappedComponent.name
    || 'Component';

  WithFoo.displayName = `withFoo(${wrappedComponentName})`;
  return WithFoo;
}
```

**6.1.6** Всегда используйте двойные кавычки `"` для JSX-атрибутов, а одинарные кавычки `'` для всего остального JS.

**6.1.7** Названия свойств именуются в `camelCase`. Если пропса является реакт компонентом, то в `PascelCase`

```
// Плохо
<Foo
  UserName="hello"
  phone_number={12345678}
/>

// Хорошо
<Foo
  userName="hello"
  phoneNumber={12345678}
  Component={SomeComponent}
/>
```

**6.1.8** Названия пропс, которые относятся к дочерним компонентам, именуются в `PascalCase` с обязательным синтаксисом: `ComponentNameProps`.

```
// ComponentA.jsx 
<div className="root">
  <h1>{{header}}</h1>
   ...
  <Item {...ItemProps}/>
</div>

// Использование ComponentA
<ComponentA 
  header="Мой компонент"
  ItemProps={{}}
/>
```

**6.1.9** Названия пропс, которые описывают логический тип данный `{Boolean}`, именуются с обязательной приставкой `is`.

```
// ComponentB.jsx
<div className="root">
 {isLoading
   ? <Spinner active />
   : <ComponentC />
  }
</div>

// Использование ComponentB
<ComponentB 
  isLoading="false"
/>
```

**6.1.10** Не используйте индексы элементов массива в качестве свойства `key`. Отдавайте предпочтение уникальному ID.

```
// Плохо
{todos.map((todo, index) =>
  <Todo
    {...todo}
    key={index}
  />
)}

// Хорошо
{todos.map(todo => (
  <Todo
    {...todo}
    key={todo.id}
  />
))}
```

**6.1.11** Для `ref` всегда используйте функции обратного вызова.

```
// Плохо
<Foo
  ref="myRef"
/>

// Хорошо
<Foo
  ref={(ref) => { this.myRef = ref; }}
/>
```

**6.1.12** Оборачивайте в скобки JSX теги, когда они занимают больше одной строки.

```
// Плохо
render() {
  return <MyComponent variant="long body" foo="bar">
           <MyChild />
         </MyComponent>;
}

// Хорошо
render() {
  return (
    <MyComponent variant="long body" foo="bar">
      <MyChild />
    </MyComponent>
  );
}

// хорошо, когда одна строка
render() {
  const body = <div>hello</div>;
  return <MyComponent>{body}</MyComponent>;
}
```

**6.1.13** Всегда возвращайте значение в методах `render`.

```
// Плохо
render() {
  (<div />);
}

// Хорошо
render() {
  return (<div />);
}
```
