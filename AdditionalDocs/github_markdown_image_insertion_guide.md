# Как в документ Markdown добавить превью изображения со стороннего url

## Проблема

В Markdown нельзя получить превью изображения путем простой вст  вки ссылки.
Есть просто скопировать и вставить ссылку, то в сохраненном документе 

## Решение

Чтобы вывести preview требуемого изображения, надо использовать его url в сочетании с HTLM тегом <a href>.

### О HTML:

#### Что такое HTML:

Это сокращение от Hypertext Markup Language.
Что означает стандартизированный язык гипертекстовой разметки документов для просмотра веб-страниц в браузере.

#### Синтаксис HTML:
Структура страницы документа HTML обозначается тегами.
Тег - это элемент разметки документа, который указывает назначение элемента:
```
<название_тега> контент </название_тега>
```
Для текущей задачи нам НЕ НУЖНО полностью создавать HTML документ.
Достаточно лишь одного из тегов, указывающих на сторонние ресурсы - <a href="URL">...</a>

##### Подробнее о HTML, синтаксисе страницы и тегах:

* https://ru.wikipedia.org/wiki/HTML
* https://www.w3schools.com/HTML/default.asp
* https://www.w3schools.com/tags/att_a_href.asp
* https://HTMLacademy.ru/blog/HTML/
* https://HTMLbook.ru/HTML
* https://HTMLacademy.ru/courses/299

### Что такое тег HTML <a> href

В HTML ссылки создаются с помощью тега <a>
Данный тег указывает на адрес документа, на который следует перейти.
Поскольку в качестве адреса ссылки может использоваться документ любого типа, то результат перехода по ссылке зависит от конечного файла. 

```
<a href="https://htmlacademy.ru">HTML Academy</a>
```
href — это атрибут, в котором мы прописываем адрес для перехода.

### Как использовать HTML тег <a> href для вывода превью изображения по ссылке:

<ol>
  <li>Берется подходящий url изображения</li>
  <li>Добавляется в одну из ниже указанных синтаксических конструкций с a href</li>
  <li>На странице сохраняются изменения в выбранном синтаксисе</li>
  <li>Если нужное изображение с preview и заголовком не появилось - нужно пробовать другую синтаксическую конструкцию</li>
  <li>В случае корректного выбора синтаксической конструкции - появляется нужное изображение с preview и заголовком</li>
</ol>


## Как встатвить на страницу GITHub ссылку на изображение с превью

Нужно взять подходящий вариант синтаксической конструкции, в которую затем - добавить ссылку на изображение.
И указать при необходимости - адрес текущей страницы

> Источник:
> https://meta.stackexchange.com/questions/2133/whats-the-recommended-syntax-for-an-image-with-a-link
> https://meta.stackexchange.com/questions/38915/creating-an-image-link-in-markdown-format



## Вариант 1 

### Образец
```
<a href="https://meta.stackoverflow.com/users/44330/jason-s">![alt text][1]</a>
[1]: https://www.gravatar.com/avatar/dd5a7ef1476fb01998a215b1642dfd07
```
### Результат

<a href="https://meta.stackoverflow.com/users/44330/jason-s">![alt text][1]</a>
[1]: https://upload.wikimedia.org/wikipedia/commons/7/72/ER_Diagram_MMORPG.png


## Вариант 2 - РЕШЕНИЕ

### Образец 

(уже работает как изображение с превью)
```
<a href="insert_current_page_lin">
   <img src="https://www.gravatar.com/avatar/dd5a7ef1476fb01998a215b1642dfd07">
</a>
```
### Результат

<a href="insert_current_page_link">
   <img src="https://upload.wikimedia.org/wikipedia/commons/7/72/ER_Diagram_MMORPG.png">
</a>

## Вариант 3

### Образец
```
[<img src="https://www.gravatar.com/avatar/dd5a7ef1476fb01998a215b1642dfd07">][2]
[2]: https://meta.stackoverflow.com/users/44330/jason-s
```

### Результат

[Образец диаграммы]
<img src="https://upload.wikimedia.org/wikipedia/commons/7/72/ER_Diagram_MMORPG.png">


### Вариант 4 (Нерабочий)

This does not work:

<a href='https://meta.stackoverflow.com/users/44330/jason-s'>![alt text][1]</a>


## Прочие бест практисы (ссылки)

https://meta.stackexchange.com/questions/2133/whats-the-recommended-syntax-for-an-image-with-a-link
https://www.markdownguide.org/hacks/ 

## Вопросы для дальнейшего изучения

Как изменить размер изображения?
