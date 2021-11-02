# 🦾 JavaScript

### Модули.

**5.1.1** Всегда используйте модули (`import/export`) вместо нестандартных модульных систем..

```
// Плохо
const AirbnbStyleGuide = require('./AirbnbStyleGuide');
module.exports = AirbnbStyleGuide.es6;

// Хорошо
import AirbnbStyleGuide from './AirbnbStyleGuide';
export default AirbnbStyleGuide.es6;

// Ещё лучше
import { es6 } from './AirbnbStyleGuide';
export default es6;
```

**5.1.2** Используйте только именованные экспорты, экспорт по умолчанию (`export default`) запрещён. Именованные экспорты вынуждают нас использовать правильное имя при импорте, таким образом мы обезопасим себя от того, что члены команды могут использовать разные имена для импорта одной и той же вещи.

```
// Плохо
export default MyComponent;

// Плохо
export { MyComponent as default }; 

// Плохо 
export default function(user) {
  alert(`Hello, ${user}!`);
}

// Хорошо
export const MyComponent;

// Хорошо
const MyComponent = () => ...
export { MyComponent };
```

**5.1.2** Не рекомендуется использовать импорт через `*` ("всё сразу"). Это гарантирует, что у вас есть единственный экспорт по умолчанию.

```
// Плохо
import * as AirbnbStyleGuide from './AirbnbStyleGuide';

// Хорошо
import AirbnbStyleGuide from './AirbnbStyleGuide';
```

**5.1.3** Импортируйте из пути только один раз.

```
// Плохо
import foo from 'foo';
// … some other imports … //
import { named1, named2 } from 'foo';

// Хорошо
import foo, { named1, named2 } from 'foo';

// good
import foo, {
  named1,
  named2,
} from 'foo';
```

**5.1.4** Не экспортируйте изменяемые переменные.

```
// Плохо
let foo = 3;
export { foo };

// Хорошо
const foo = 3;
export { foo };
```

**5.1.6** Импорты на нескольких строках должны быть с отступами как у многострочных литералов массива и объекта.

```
// Плохо
import {longNameA, longNameB, longNameC, longNameD, longNameE} from 'path';

// Хорошо
import {
  longNameA,
  longNameB,
  longNameC,
  longNameD,
  longNameE,
} from 'path';
```

**5.1.7** Не указывайте расширение импортируемых файлов.

```
// Плохо
import foo from './foo.js';
import bar from './bar.jsx';
import baz from './baz/index.jsx';

// Хорошо
import foo from './foo';
import bar from './bar';
import baz from './baz';
```

### Отступы, пробелы и переносы.

**5.2.1** Для отступов используются два пробела. Знак табуляции не используется.

```
// Плохо
function foo() {
∙∙∙∙let name;
}

// Плохо
function bar() {
∙let name;
}

// Хорошо
function baz() {
∙∙let name;
}
```

**5.2.2** Файл должен заканчиваться пустой строкой.

**5.2.3** Строка не должна заканчиваться пробелами.

**5.2.4** Максимальная длина строки 100 символов, остальное переносится.

**5.2.5** В комментариях текст отбивается пробелом от начала комментария.

**5.2.6** После двоеточий и точек с запятыми ставятся пробелы. Перед ними — не ставятся.

**5.2.7** Смысловые блоки кода отделяются друг от друга не более чем одной пустой строкой.

```
//Плохо
if (foo) {
  return bar;
}
return baz;

//Плохо
if (foo) {
  return bar;
}


return baz;

// Хорошо
if (foo) {
  return bar;
}

return baz;
```

**5.2.8** Для отступов ключевых слов, операторов и т. д. используется не более одного пробела.

```
// Плохо
function test(){
  console.log('test');
}

// Хорошо
function test() {
  console.log('test');
}

// Плохо
dog.set('attr',{
  age: '1 year',
  breed: 'Bernese Mountain Dog',
});

// Хорошо 
dog.set('attr', {
  age: '1 year',
  breed: 'Bernese Mountain Dog',
});

// Плохо
const x=y+5;

// Хорошо
const x = y + 5;
```

**5.2.9** Открывающие скобки блоков кода находятся на одной строке с оператором, который их использует.

**5.2.10** В однострочных блоках кода, код отделен от открывающей и закрывающей скобки пробелом.

```
// Хорошо
if (condition) {
  // code
}

//  Плохо
if (condition)
{
  // code
}
```

**5.2.11** В однострочных массивах скобки не отделяются пробелами, первое значение идёт непосредственно после открывающей скобки, а закрывающая скобка идёт непосредственно после последнего значения массива. После запятой всегда должен ставиться пробел, если запятая не в конце строки.

**5.2.12** Обязательно использовать запятую в конце списков, объектов или перечислений параметров функции.

```
// Хорошо
const foo = {
  a: 1,
  b: 2,
};

const bar = [1, 2];

// Плохо
const foo = {
  a: 1,
  b: 2
};

const bar = [
  1, 
  2
];
```

**5.2.13** В однострочных объектах и при деструктуризации фигурные скобки отделяются пробелами от содержимого.

```
// Хорошо
const foo = { a: 1 };
const { a, b } = someObject;

// Плохо
const foo = {a: 1};
const {a, b} = someObject;
```

**5.2.14** Значения в круглых скобках не отделяются пробелами (например: аргументы функции, условие оператора `if`).

```
// Хорошо
function bar(foo) {
  return foo;
}

// Плохо
function bar( foo ) {
  return foo;
}

// Хорошо
if (foo) {
  console.log(foo);
}

// Плохо
if ( foo ) {
  console.log(foo);
}
```

**5.2.15** Значения в квадратных скобках не отделяются пробелами.

```
// Плохо
const foo = [ 1, 2, 3 ];
console.log(foo[ 0 ]);

// Хорошо
const foo = [1, 2, 3];
console.log(foo[0]);
```

**5.2.16** Используйте переносы строк и отступы, когда делаете длинные цепочки методов (больше 2 методов). Ставьте точку в начале строки, чтобы дать понять, что это не новая инструкция, а продолжение цепочки.

```
// Плохо
$('#items').find('.selected').highlight().end().find('.open').updateCount();

// Плохо
$('#items').
  find('.selected').
    highlight().
    end().
  find('.open').
    updateCount();

// Хорошо
$('#items')
  .find('.selected')
    .highlight()
    .end()
  .find('.open')
    .updateCount();
```

### Строки.

**5.3.1** В строках используются одинарные кавычки.

**5.3.2** Разрешено использовать строковые шаблоны в случаях, когда необходима интерполяция.

**5.3.3** В строках запрещено указывать код спецсимволов в восьмеричной системе счисления.

```
// Плохо
const foo = 'Copyright \251';

// Хорошо
const foo = 'Copyright \u00A9';
```

### Именование.

**5.4.1** Избегайте названий из одной буквы. Имя должно быть наглядным.

```
 // Плохо
function q() {}

// Хорошо
function query() {}
```

**5.4.2** Запрещено называть переменные и свойства ключевыми словами JS.

**5.4.3** Все переменные должны быть названы в `camelCase`. Исключения составляют константы, которые должны именоваться прописными буквами в константном регистре (`CONSTANT_CASE`) и названия классов, функций-конструкторов и перечислений, которые именуются с заглавной буквы (`PascalCase`).

```
// Плохо
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// Хорошо
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

**5.4.4** Не используйте `_` в начале или в конце названий. JavaScript не имеет концепции приватности свойств или методов. Хотя подчёркивание в начале имени является распространённым соглашением, которое показывает «приватность», фактически эти свойства являются такими же доступными, как и часть вашего публичного API. Это соглашение может привести к тому, что разработчики будут ошибочно думать, что изменения не приведут к поломке или что тесты не нужны.

```
// Плохо
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';
this._firstName = 'Panda';

// Хорошо
this.firstName = 'Panda';
```

**5.4.5** Не сохраняйте ссылку на `this`. Используйте стрелочные функции или метод `bind()`.

```
// Плохо
function foo() {
  const self = this;
  return function () {
    console.log(self);
  };
}

// Плохо
function foo() {
  const that = this;
  return function () {
    console.log(that);
  };
}

// Хорошо
function foo() {
  return () => {
    console.log(this);
  };
}
```

**5.4.6** Название файла точно должно совпадать с именем его экспорта по умолчанию.

```
// 1 файл
class CheckBox {
  // ...
}
export default CheckBox;

// 2 файл
export default function fortyTwo() { return 42; }

// 3 файл
export default function insideDirectory() {}

// импорт
// Плохо
import CheckBox from './checkBox'; // PascalCase import/export, camelCase filename
import FortyTwo from './FortyTwo'; // PascalCase import/filename, camelCase export
import InsideDirectory from './InsideDirectory'; // PascalCase import/filename, camelCase export

// Плохо
import CheckBox from './check_box'; // PascalCase import/export, snake_case filename
import forty_two from './forty_two'; // snake_case import/filename, camelCase export
import inside_directory from './inside_directory'; // snake_case import, camelCase export
import index from './inside_directory/index'; // requiring the index file explicitly
import insideDirectory from './insideDirectory/index'; // requiring the index file explicitly

// Хорошо
import CheckBox from './CheckBox'; // PascalCase export/import/filename
import fortyTwo from './fortyTwo'; // camelCase export/import/filename
import insideDirectory from './insideDirectory'; // camelCase export/import/directory name/implicit "index"
// ^ supports both insideDirectory.js and insideDirectory/index.js
```

**5.4.7** Используйте `PascalCase`, когда экспортируете конструктор / класс / синглтон / библиотечную функцию / объект.

```
const AirbnbStyleGuide = {
  es6: {
  },
};

export default AirbnbStyleGuide;
```

**5.4.8** Сокращения или буквенные аббревиатуры всегда должны быть в верхнем или нижнем регистре.

```
// Плохо
import SmsContainer from './containers/SmsContainer';

// Плохо
const HttpRequests = [
  // ...
];

// Хорошо
import SMSContainer from './containers/SMSContainer';

// Хорошо
const HTTPRequests = [
  // ...
];

// Хорошо
const httpRequests = [
  // ...
];

// Ещё лучше
import TextMessageContainer from './containers/TextMessageContainer';

// Ещё лучше
const requests = [
  // ...
];
```

### Объявление переменных и функций.

**5.5.1** При объявлении переменных используются ключевые слова `let` и `const`. Переменные, объявленные через `var` запрещены.

**5.5.2** Не рекомендуется использовать множественное объявление через одно ключевое слово. Для каждой переменной используется отдельный `let` или `const`.

```
// Плохо
const a = 1, b = 2;

// Хорошо
const a = 1;
const b = 2;
```

**5.5.3** При объявлении множества переменных, не мешайте их между собой. Вначале перечисляйте все `const`, после этого все `let`.

```
// Плохо
let i;
const items = getItems();
let dragonball;
const goSportsTeam = true;
let len;

// Хорошо
const goSportsTeam = true;
const items = getItems();
let dragonball;
let i;
let length;
```

**5.5.4** Запрещено переопределение функций, созданных с помощью функционального объявления (function declaration)

```
// Плохо
function myFunc() {};
myFunc = 2;
```

### Объекты.

**5.6.1** Для создания объекта используйте литеральную нотацию `{}`.

```
// Плохо
const item = new Object();

// Хорошо
const item = {};
```

**5.6.2** Используйте сокращённую запись метода объекта.

```
// Плохо
const atom = {
  value: 1,

  addValue: function (value) {
    return atom.value + value;
  },
};

// Хорошо
const atom = {
  value: 1,

  addValue(value) {
    return atom.value + value;
  },
};
```

**5.6.3** Используйте сокращённую запись свойств объекта.

**5.6.4** Группируйте ваши сокращённые записи свойств в начале объявления объекта.

```
// Плохо
const obj = {
  episodeOne: 1,
  lukeSkywalker: lukeSkywalker,
  episodeThree: 2,
  anakinSkywalker: anakinSkywalker,
};

// good
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
};
```

**5.6.5** Вместо `Object.assign()` используется spread оператор.

```
// Плохо
const original = { a: 1, b: 2 };
const copy = Object.assign({}, original, { c: 3 });

// Хорошо
const original = { a: 1, b: 2 };
const copy = { ...original, c: 3 };
```

### Массивы.

**5.7.1** Для создания массива используйте литеральную нотацию `[]`.

```
// Плохо
const items = new Array();

// Хорошо
const items = [];
```

**5.7.2** Для добавления элемента в массив используйте `Array.push` вместо прямого присваивания.

```
// Плохо
someStack[someStack.length] = 'abracadabra';

// Хорошо
someStack.push('abracadabra');
```

**5.7.3** Для копирования массивов используйте оператор spread.

```
// Плохо
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i += 1) {
  itemsCopy[i] = items[i];
}

// Хорошо
const itemsCopy = [...items];
```

**5.7.4** Для преобразования итерируемого объекта в массив используйте spread оператор вместо `Arra.from`

```
const foo = document.querySelectorAll('.foo');

// Хорошо
const nodes = Array.from(foo);

// Ещё лучше
const nodes = [...foo];
```

**5.7.5** Пользуйтесь деструктуризацией массивов.

```
const arr = [1, 2, 3, 4];

// Плохо
const first = arr[0];
const second = arr[1];

// Хорошо
const [first, second] = arr;
```

### Функции.

**5.8.1** Отдавайте приоритет функциональным выражениям (function expresson) вместо объявлений функций (function declaration).

**5.8.2** Отдавайте приоритет стрелочным функциям.

**5.8.3** Никогда не пользуйтесь конструтором `Function`.

```
// Плохо
function foo() {
  // ...
}

// Плохо
const foo = function () {
  // ...
};

// Хорошо
const short = function foo() {
  // ...
};

// Так себе
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// Хорошо
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

**5.8.4** Самовызывающиеся функции оборачиваются в круглые скобки (IIFE).

```
(function () {
  console.log('');
}());
```

**5.8.5** Используйте rest оператор вместо коллекции `arguments`.

```
// Плохо
function concatenateAll() {
  const args = Array.prototype.slice.call(arguments);
  return args.join('');
}

// Хорошо
function concatenateAll(...args) {
  return args.join('');
}
```

**5.8.6** Используйте синтаксис записи аргументов по умолчанию, а не изменяйте аргументы функции.

```
// Очень плохо
function handleThings(opts) {
  opts = opts || {};
  // ...
}

// Плохо
function handleThings(opts) {
  if (opts === void 0) {
    opts = {};
  }
  // ...
}

// Хорошо
function handleThings(opts = {}) {
  // ...
}

// Плохо
function f1(obj) {
  obj.key = 1;
}

// Хорошо
function f2(obj) {
  const key = Object.prototype.hasOwnProperty.call(obj, 'key') ? obj.key : 1;
}
```

**5.8.7** Аргументы со значением по умолчанию записываются в конце.

```
// Плохо
function handleThings(opts = {}, name) {
  // ...
}

// Хорошо
function handleThings(name, opts = {}) {
  // ...
}
```

**5.8.8** Аргументы стрелочной функции всегда оборачиваются в круглые скобки.

```
// Плохо
[1, 2, 3].map(x => x * x);

// Хорошо
[1, 2, 3].map((x) => x * x);
```

**5.8.9** Если тело функции состоит из одного оператора, возвращающего выражение без побочных эффектов, то опустите фигурные скобки и используйте неявное возвращение. В противном случае, сохраните фигурные скобки и используйте оператор `return`.

```
// Плохо
[1, 2, 3].map((number) => {
  return {
   result: number;
  }
});

// Хорошо
[1, 2, 3].map((number, index) => ({
  result: number,
}));
```

### Операторы сравнения и равенства.

**5.9.1** Используйте строгое сравнение.

```
/* Хорошо */
if(foo === baz) {}
if(foo !== baz) {}

/* Плохо */
if(foo == baz) {}
if(foo != baz) {}
```

**5.9.2** Используйте сокращения для булевских типов, а для строк и чисел применяйте явное сравнение.

```
// Плохо
if (isValid === true) {
  // ...
}

// Хорошо
if (isValid) {
  // ...
}

// Плохо
if (name) {
  // ...
}

// Хорошо
if (name !== '') {
  // ...
}

// Плохо
if (collection.length) {
  // ...
}

// Хорошо
if (collection.length > 0) {
  // ...
}
```

**5.9.3** При смешивании операторов, помещайте их в круглые скобки.

```
// Плохо
const foo = a && b < 0 || c > 0 || d + 1 === 0;

// Плохо
const bar = a + b / c * d;

// Хорошо
const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

// Хорошо
const bar = a + (b / c) * d;
```

**5.9.4** Тернарные операторы не должны быть вложены и в большинстве случаев должны быть расположены на одной строке.

```
// Плохо
const foo = maybe1 > maybe2
  ? "bar"
  : value1 > value2 ? "baz" : null;

// split into 2 separated ternary expressions
const maybeNull = value1 > value2 ? 'baz' : null;

// Хорошо
const foo = maybe1 > maybe2
  ? 'bar'
  : maybeNull;

// Ещё лучше
const foo = maybe1 > maybe2 ? 'bar' : maybeNull;
```
