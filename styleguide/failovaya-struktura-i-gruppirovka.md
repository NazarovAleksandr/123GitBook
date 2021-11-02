# 🗄 Файловая структура и группировка

**1.1** В корне проекта/модуля находятся общие папки/файлы для всех компонентов такие, как глобальные хелперы, картинки, шрифты, зависимости (vendors), настройка хранилища и т.д.

**1.2** Файлы должны группироваться по смыслу. Если речь про отдельный компонент, то все связанные с ним файлы должны лежать рядом. К таким файлам можно отнести: локализация, тесты, стили, сторис (сторибук), настройка хранилища. Такую "папку" необходимо рассматривать как самостоятельную единицу, которую можно переместить или удалить и остальной код не пострадает. Ещё одно приемущество такого подхода заключается в том, что не нужно постоянно перемещаться по файловой структуре в поисках необходимого файла.

**1.3** Название файла React компонента должно быть в `PascalCase`, соответствовать названию самого компонента.

```
<!-- Хорошо -->
 project/
  modules/
    UserPage/
      UserPage.tsx
      index.ts
      demo/
      store/
      components/
        UserList/
          UserList.modules.scss
          UserList.tsx
          UserList.test.ts
          locale.json
          index.ts
        UserCard/
          UserCard.tsx
          UserCard.test.ts
          demo/
            UserCard.stories.tsx
          locale.json
          index.ts
     ...  
    config/
    vendors/
    assets/
    styles/
    index.ts


<!-- Плохо -->
project/
  components/
    user-page/
     ...
  tests/
    user-card.test.ts
    user-list.test.ts
  styles/
    user-list.modules.scss
    user-page.modules.scss
  ...
  index.ts
```
