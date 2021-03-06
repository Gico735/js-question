# GIT
## Основы Git - Запись изменений в репозиторий
```sh 
  git clone {repository:url} [dir name] // Клонировать репозиторий из удаленного  
  git pull // Получение данных из удаленного репозитория 
  git add . // Добавить все изменения в коммит
  git commit -m 'fix' // Сформировать коммит с сообщением "fix"
  git push  // Отправить данные на удаленный репозиторий
```

#Сборщики
## Gulp
  Что такое gulp?
  **Gulp — это таск-менеджер** для автоматического выполнения часто используемых задач (*например, минификации, тестирования, объединения файлов*), написанный на языке программирования JavaScript. Программное обеспечение использует командную строку для запуска задач, определённых в файле Gulpfile. Создан как ответвление от проекта Grunt, чтоб взять из него лучшие практики. Распространяется через менеджер пакетов NPM под MIT лицензией.

  От Grunt отличается тем, что код задач записывается JavaScript кодом, а не в стиле конфигурационного файла[5].

  На 2017-й год насчитывается более 3100 плагинов для Gulp[6].

  Взаимодействия между частями программы реализуется через оператор .pipe(), выполняя по одной задаче за раз, не затрагивая исходные файлы, до конца процедуры. Это даёт возможность комбинации плагинов в любой последовательности и количестве.

  Так же в Gulp усовершенствована система сборки. Это значит, что помимо запуска задач, можно также копировать файлы с места на место, компилировать и развёртывать проект в новом окружении.

# 'use strict'
Что такое ``` 'use sctict' ``` ?
Как использовать на отдельных учасках кода?

# ES 2015
В ES-2015 предусмотрены новые способы объявления переменных: через let и const вместо var.
Область видимости переменной let – блок {...}.
Переменная let видна только после объявления.
При использовании в цикле, для каждой итерации создаётся своя переменная.
Переменная const – это константа, в остальном – как let.

## Деструктуризация
```let [firstName, lastName] = ["Илья", "Кантор"];```
### Оператор «spread»

```js
'use strict';
let [firstName, lastName, ...rest] = "Юлий Цезарь Император Рима".split(" ");

alert(firstName); 
alert(lastName);  
alert(rest);   

let obj = {'a' : 1, 'b' : 2}
let newObj = {'c' : 3, ...obj, 'd' : 4}
```

### Функции через =>
```js
'use strict';

let inc = x => x+1;
alert( inc(1) );
/***/
let inc2 = x => {
    x+1
}
alert( inc2(1) );
```



### События мыши:
 - click – происходит, когда кликнули на элемент левой кнопкой мыши
 - contextmenu – происходит, когда кликнули на элемент правой кнопкой мыши
 - mouseover – возникает, когда на элемент наводится мышь
 - mousedown и mouseup – когда кнопку мыши нажали или отжали
 - mousemove – при движении мыши


Какие есть способы повесить обработчик событий?
```html
HTML
<input type="button" id="button" onclick="sayThanks()" />
```
```js
JS
document.body.setAttribute('onclick', function() { alert(1) });
elem.onclick = function() { alert("Привет"); };
elem.addEventListener("click", handler1);
```
### Делегирование событий

### Отмена действия браузера
```event.preventDefault()```
### Отмена всплытия события
```event.stopPropagation()```

#### 1.
```html
<button data-attr>1</button>
<button data-attr>2</button>
<script>
  document.onclick = function(event) {
    if (!event.target.hasAttribute('data-attr')) return;
    var counter = event.target;
    counter.innerHTML++;
  };
</script>
```
#### 2.
```html
<button data-toggle-id="subscribe-mail">
  text
</button>
<form id="subscribe-mail" hidden>
  Ваша почта: <input type="email">
</form>
<script>
  document.onclick = function(event) {
    var target = event.target;
    var id = target.getAttribute('data-toggle-id');
    if (!id) return;
    var elem = document.getElementById(id);
    elem.hidden = !elem.hidden;
  };
</script>
```
