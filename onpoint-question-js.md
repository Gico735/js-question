# GIT
## Основы Git - Запись изменений в репозиторий
```sh 
  git pull // Получение данных из удаленного репозитория 
  git add . // Добавить все изменения в коммит
  git commit -m 'fix' // Сформировать коммит с сообщением "fix"
  git push  // Отправить данные на удаленный репозиторий
```

# BASH

# 'use strict'
Что такое ``` 'use sctict' ``` ?
Как использовать на отдельных учасках кода?
# Правила именования
camelCase
# Типы
## Число «number»
```alert( 1 / 0 );```
```alert( "нечисло" * 2 );```
Какой будет результат?

## Строка «string»
В JavaScript одинарные и двойные кавычки равноправны. Можно использовать или те или другие.
Как можно добавить кавычки в троковое значение?
# Булевый (логический) тип «boolean»
# Объекты «object»

# ES 2015
В ES-2015 предусмотрены новые способы объявления переменных: через let и const вместо var.
Область видимости переменной let – блок {...}.
Переменная let видна только после объявления.
При использовании в цикле, для каждой итерации создаётся своя переменная.
Переменная const – это константа, в остальном – как let.

## Деструктуризация
```let [firstName, lastName] = ["Илья", "Кантор"];```
### Оператор «spread»

```
'use strict';
let [firstName, lastName, ...rest] = "Юлий Цезарь Император Рима".split(" ");

alert(firstName); 
alert(lastName);  
alert(rest);   

let obj = {'a' : 1, 'b' : 2}
let newObj = {'c' : 3, ...obj, 'd' : 4}
```

### Функции через =>
```
'use strict';
let inc = x => x+1;
alert( inc(1) );
let inc2 = x => {
    x+1
}
alert( inc2(1) );
```


# Введение в браузерные события
### События мыши:
 - click – происходит, когда кликнули на элемент левой кнопкой мыши
 - contextmenu – происходит, когда кликнули на элемент правой кнопкой мыши
 - mouseover – возникает, когда на элемент наводится мышь
 - mousedown и mouseup – когда кнопку мыши нажали или отжали
 - mousemove – при движении мыши

### События на элементах управления:
 - submit – посетитель отправил форму <form>
 - focus – посетитель фокусируется на элементе, например нажимает на <input>

### Клавиатурные события:
 - keydown – когда посетитель нажимает клавишу
 - keyup – когда посетитель отпускает клавишу

### События документа:
 - DOMContentLoaded – когда HTML загружен и обработан, DOM документа полностью построен и доступен.

### События CSS:
 - transitionend – когда CSS-анимация завершена.

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

### Приём проектирования "поведение"
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
