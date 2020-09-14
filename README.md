CSS или каскадная таблица стилей нужна, чтобы указать HTML, как отображать разметку.

Особенность: CSS чувствителен к регистру, поэтому нужно быть внимательным.

CSS позволяет контролировать:
- Цвет;
- Шрифты; 
- Позиционирование элементов;
- Интервал между элементами;
- Калибровку;
- Различные украшения элементов;
- Переходы.

Подключить CSS можно непосредственно к html элементу или отдельным файлом к html документу. Предпочтительнее второй способ.
Первым способом подключение происходит через тег style в html теге. Например: 
```html
<img style="color: fff" src=""/>
```
Можно также подключить общий стиль для документа в теге ```<head>```. Для этого указывается тег ```<style>Здесь прописываются стили</style>```.
Вторым способом подключение происходит через отдельный файл с расширением .css. Обычно его называют style.css и подключают к html документу в теге ```<head>``` через тег ```<link>```. Например:
```html
<!-- это подключение файла со стилями -->
<link rel="stylesheet" href="css/style.css">
<!-- это подключение внешнего шрифта -->
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&family=Roboto+Mono:wght@400;700&display=swap" rel="stylesheet">
```

В основном управление стилями происходит через классы. Для элементов html прописывается класс и уже для класса в таблице стилей прописывается, то как он будет отображаться. Это позволяет применять один и тот же стиль к разным элементам и избежать дублирования кода. Например:
```html
<!-- когда класс прописан в html документе, то в css он записывается начиная с точки -->
<!-- но если стиль применяется к элементу в целом, то точка не нужна, как пример h2 -->
<style>
  .blue-text {
    color: blue;
  }
  h2 {
    font-size: 20px;
  }
</style>

<h2 class="blue-text">CatPhotoApp</h2>
<main>
  <p class="blue-text">Click here to view more <a href="#">cat photos</a>.</p>
```
Если к элементу применяется несколько классов, то они идут по очереди через проблел. Например: ```class="blue-text red-style"```.

К элементам можно применять стили помимо класса с помощью id. Например: ```<h2 id="cat-photo-app">```
Использование атрибутов id дает несколько преимуществ: вы можете использовать id для стилизации одного элемента, а позже использовать их для выбора и изменения определенных элементов с помощью JavaScript. Атрибуты id должны быть уникальными. 

ВАЖНО!:  ID не может использоваться повторно и должен применяться только к одному элементу. ID также имеет более высокую важность, чем класс, поэтому, если оба применяются к одному и тому же элементу и имеют конфликтующие стили, будут применяться стили ID.



Основные теги CSS.

```color: red;``` - позволяет изменять цвет текста в элементе на тот, что указан после двоеточия.

```font-size: 30px;``` - позволяет изменять размер шрифта.

```font-family: monospace sans-serif;``` - позволяет устанавливать шрифт для элемента. Например: тут monospace шрифт, а sans-serif вид шрифта без засечек у букв.
Шрифты можно выбрать стандартные или из онлайн библиотеки. Например: https://fonts.google.com/
Google Fonts - это бесплатная библиотека веб-шрифтов, которую вы можете использовать в своем CSS, ссылаясь на URL-адрес шрифта. Пример импорта шрифта есть выше.
```font-family: FAMILY_NAME, GENERIC_NAME;``` - можно указывать два шрифта. Первый по умолчанию и второй запасной, если первый не работает.
Особенность: Имена семейств чувствительны к регистру и должны быть заключены в кавычки, если в имени есть пробел. Например, вам нужны кавычки, чтобы использовать шрифт «Open Sans», но не использовать шрифт Lobster.

```width: 500px;``` - позволяет задать ширину элемента.

```border: red solid 5px;``` - позволяет создать рамку вокруг элемента. Можно записывать, как в примере свойства в строчку или по отдельности. Например: 
```html
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
</style>
```
У рамки есть три свойства: ширина, цвет и стиль.

```border-radius: 10px;``` - позволяет убрать острые края и скруглить их на указанное значение. Значение может быть в пикселях или в процентах.

```background-color: green;``` - позволяет задать фоновый цвет элемента.


