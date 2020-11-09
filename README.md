<h1><b>CSS</b></h1>

<hr />
<hr />

<h2>Содержание:</h2>
<ol>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D0%BE%D0%B1%D1%89%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F">Общая информация</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-css">Подключение CSS</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%82%D0%B8%D0%BB%D1%8F%D0%BC%D0%B8">Управление стилями</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D1%81%D0%B5%D0%BB%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D1%8B">Селекторы</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D1%81%D1%82%D0%B2%D0%BE%D0%BC-html">Управление пространством HTML</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D0%BF%D1%80%D0%BE-%D1%86%D0%B2%D0%B5%D1%82">Про цвет</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D1%8B%D0%B5-%D1%82%D0%B5%D0%B3%D0%B8-css">Основные теги CSS</a></li>
  <li><a href="https://github.com/sanikitin/Notes_on_CSS#%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D0%B5%D1%81%D0%BD%D0%BE%D1%81%D1%82%D0%B8">Интересности</a></li>
</ol>

<hr />
<hr />

<h3><b>Общая информация</b></h3>

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

<hr />
<hr />

<h3><b>Подключение CSS</b></h3>

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

<hr />
<hr />

<h3><b>Управление стилями</b></h3>

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

ВАЖНО!: В CSS работает наследственность. То есть, если к body применены стили и в этом элементе лежит h1, то он будет использовать стили из элемента body, если не заданы другие. Пример:
```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
</style>
<h1>Hello World!</h1>
```
Важен порядок объявлений классов в разделе <style>. Второе объявление всегда будет иметь приоритет перед первым. Каждый последующий объявленный класс будет переопределять класс предыдущий, если они применены к одному элементу. 
ВАЖНО!: Порядок подключения классов к элементу не важен. Если первый подключенный класс объявлен раньше второго, то он будет переопределен. Это происходит так как браузер читает стили сверху вниз по очереди.

Также, важно знать, что ID имеет приоритет при подключении и объявлении. Поэтому, не важно где он подключен или объявлен. 
Над классами и ID имеет приоритет и классическое объявление стиля в элементе. Например: ```<h1 style="color: green;">```.

Но, чтобы задать максимальный приоритет элементу можно использовать ключевое слово !important. Это позволит обезопасить ваши персональные стили от стилей подключаемых библиотек. Пример синтаксиса:
```css
.pink-text {
    color: pink !important;
  }
```

К элементам можно применять стили помимо класса с помощью id. Например: ```<h2 id="cat-photo-app">```
Использование атрибутов id дает несколько преимуществ: вы можете использовать id для стилизации одного элемента, а позже использовать их для выбора и изменения определенных элементов с помощью JavaScript. Атрибуты id должны быть уникальными. 

Чтобы применить стили к элементу по ID нужно использовать не точку, а #. Например: 
```css
#cat-photo-element {
  background-color: green;
}
```

ВАЖНО!:  ID не может использоваться повторно и должен применяться только к одному элементу. ID также имеет более высокую важность, чем класс, поэтому, если оба применяются к одному и тому же элементу и имеют конфликтующие стили, будут применяться стили ID.

<hr />
<hr />

<h3><b>Селекторы</b></h3>

Class и ID называются селекторами CSS (CSS Selectors). Существуют и другие селекторы CSS, которые можно использовать для выбора пользовательских групп элементов для стилизации. 

Селектор атрибута ```[attr = value]``` - этот селектор сопоставляет и стилизует элементы с определенным значением атрибута. Например, приведенный ниже код изменяет поля всех элементов с типом атрибута и соответствующим значением радио:
```css
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
```

<hr />
<hr />

<h3><b>Управление пространством HTML</b></h3>

Три важных свойства управляют пространством, окружающим каждый элемент HTML: отступ (padding), граница (border) и поле (margin).
- Отступ (padding) элемента контролирует расстояние между содержимым элемента и его границей.
- Поле (margin) элемента контролирует количество пространства между границей элемента и окружающими элементами.
Картинка, которая хорошо показывает, что есть что.
![Site](https://github.com/sanikitin/Notes_on_CSS/raw/master/2020-09-14_20-14-40.png)

Особенности

- Если вы установить для поля отрицательное значение, элемент станет больше.
- CSS позволяет вам управлять заполнением всех четырех отдельных сторон элемента с помощью свойств padding-top, padding-right, padding-bottom и padding-left. Аналогично для margin. Но можно указывать и в одну строчку. Пример: ```padding: 10px 20px 10px 20px;```. Значения работают как часы: сверху, справа, снизу, слева.

В дополнение к пикселям в CSS есть несколько различных вариантов единиц длины. Два основных типа единиц длины - абсолютные и относительные. Абсолютные единицы привязаны к физическим единицам длины. Единицы абсолютной длины приблизительно соответствуют фактическому измерению на экране, но есть некоторые различия в зависимости от разрешения экрана. Относительные единицы, такие как em или rem, относятся к другому значению длины. Например, em зависит от размера шрифта элемента. Если вы используете его для установки самого свойства font-size, оно относительно родительского font-size. 

<hr />
<hr />

<h3><b>Про цвет</b></h3>

В CSS можно писать цвет словом или использовать 6 шестнадцатеричных цифр для представления цветов, по две для красного (R), зеленого (G) и синего (B) компонентов. Например, # 000000 - черный цвет, а также минимальное возможное значение. Здесь вы можете найти дополнительную информацию о цветовой системе RGB (https://en.wikipedia.org/wiki/RGB_color_model). Пример цвета в 16-ричной системе:
```css
body {
  color: #000000;
}
```
Особеноость: Код из 6 цифр можно сократить до трех. Шестнадцатеричный код red # FF0000 можно сократить до # F00. Эта сокращенная форма дает одну цифру для красного, одну цифру для зеленого и одну цифру для синего.

Также, можно использовать систему RGB для указания цвета. Синтаксис при этом выглядит так:
```css
body {
  background-color: rgb(255, 165, 0);
}
```

<hr />
<hr />

<h3><b>Основные теги CSS.</b></h3>


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

```--penguin-skin: gray;``` - создание и присвоение переменной значения. Это позволит использовать эту переменную во всем CSS файле далее. Присвоение значения переменной другим элементам происходит с помощью синтаксиса:
```css
.penguin-top {
    background: var(--pengiun-skin);
  }
```
При использовании вашей переменной в качестве значения свойства CSS вы можете прикрепить запасное значение, к которому ваш браузер вернется, если данная переменная недействительна. Особенность: Этот резервный вариант не используется для повышения совместимости браузеров и не будет работать в браузерах IE. Скорее, он используется для того, чтобы браузер отображал цвет, если он не может найти вашу переменную.
Синтаксис: 
```css
.penguin-top {
    background: var(--penguin-skin, black);
  }
```
ВАЖНО!: Использование переменных может привести к тому, что некоторые браузеры не будут поддерживать их. Поэтому, нужно улучшать совместимость с другими браузерами добавлением стандартных способов, чтобы больше браузеров смогли их отобразить. В примере ниже фон объявляется по обычному прямо перед объявлением через переменную, чтобы браузер, который не поддерживает переменные мог загрузить фон стандартным способом:
```css
<style>
  :root {
    --red-color: red;
  }
  .red-box {
    background: red;
    background: var(--red-color);
    height: 200px;
    width:200px;
  }
</style>
<div class="red-box"></div>
```
Переменные CSS наследуются, как и обычные свойства. Чтобы использовать наследование, переменные CSS часто определяются в элементе: root. ```: root``` - это селектор псевдокласса, который соответствует корневому элементу документа, обычно элементу html. Создавая свои переменные в: root, они будут доступны глобально, и к ним можно будет получить доступ из любого другого селектора в таблице стилей.
По сути root используется, как хранилище переменных с открытым доступом. Однако, если потребовалось изменить переменную дальше в структуре, то её можно переопределить, присвоив новое значение. 

Переменные и root удобно применять при медиа запросах. Можно переопределить root, а остальные стили ниже будут использовать нужные параметры в зависимости от соблюдения условий. Пример: 
```css
<style>
  :root {
    --penguin-size: 300px;
    --penguin-skin: gray;
    --penguin-belly: white;
    --penguin-beak: orange;
  }

  @media (max-width: 350px) {
    :root {
      --penguin-size: 200px;
      --penguin-skin: black;
    }
  }
```

<hr />
<hr />

<h3><b>Интересности</b></h3>

- Пингвин
<details>

```html
<style>
  .penguin {

    /* Only change code below this line */
    --penguin-skin: gray;
    --penguin-belly: white;
    --penguin-beak: orange;
    /* Only change code above this line */

    position: relative;
    margin: auto;
    display: block;
    margin-top: 5%;
    width: 300px;
    height: 300px;
  }

  .penguin-top {
    top: 10%;
    left: 25%;
    background: var(--penguin-skin, gray);
    width: 50%;
    height: 45%;
    border-radius: 70% 70% 60% 60%;
  }

  .penguin-bottom {
    top: 40%;
    left: 23.5%;
    background: var(--penguin-skin, gray);
    width: 53%;
    height: 45%;
    border-radius: 70% 70% 100% 100%;
  }

  .right-hand {
    top: 0%;
    left: -5%;
    background: var(--penguin-skin, gray);
    width: 30%;
    height: 60%;
    border-radius: 30% 30% 120% 30%;
    transform: rotate(45deg);
    z-index: -1;
  }

  .left-hand {
    top: 0%;
    left: 75%;
    background: var(--penguin-skin, gray);
    width: 30%;
    height: 60%;
    border-radius: 30% 30% 30% 120%;
    transform: rotate(-45deg);
    z-index: -1;
  }

  .right-cheek {
    top: 15%;
    left: 35%;
    background: var(--penguin-belly, white);
    width: 60%;
    height: 70%;
    border-radius: 70% 70% 60% 60%;
  }

  .left-cheek {
    top: 15%;
    left: 5%;
    background: var(--penguin-belly, white);
    width: 60%;
    height: 70%;
    border-radius: 70% 70% 60% 60%;
  }

  .belly {
    top: 60%;
    left: 2.5%;
    background: var(--penguin-belly, white);
    width: 95%;
    height: 100%;
    border-radius: 120% 120% 100% 100%;
  }

  .right-feet {
    top: 85%;
    left: 60%;
    background: var(--penguin-beak, orange);
    width: 15%;
    height: 30%;
    border-radius: 50% 50% 50% 50%;
    transform: rotate(-80deg);
    z-index: -2222;
  }

  .left-feet {
    top: 85%;
    left: 25%;
    background: var(--penguin-beak, orange);
    width: 15%;
    height: 30%;
    border-radius: 50% 50% 50% 50%;
    transform: rotate(80deg);
    z-index: -2222;
  }

  .right-eye {
    top: 45%;
    left: 60%;
    background: black;
    width: 15%;
    height: 17%;
    border-radius: 50%;
  }

  .left-eye {
    top: 45%;
    left: 25%;
    background: black;
    width: 15%;
    height: 17%;
    border-radius: 50%;
  }

  .sparkle {
    top: 25%;
    left: 15%;
    background: white;
    width: 35%;
    height: 35%;
    border-radius: 50%;
  }

  .blush-right {
    top: 65%;
    left: 15%;
    background: pink;
    width: 15%;
    height: 10%;
    border-radius: 50%;
  }

  .blush-left {
    top: 65%;
    left: 70%;
    background: pink;
    width: 15%;
    height: 10%;
    border-radius: 50%;
  }

  .beak-top {
    top: 60%;
    left: 40%;
    background: var(--penguin-beak, orange);
    width: 20%;
    height: 10%;
    border-radius: 50%;
  }

  .beak-bottom {
    top: 65%;
    left: 42%;
    background: var(--penguin-beak, orange);
    width: 16%;
    height: 10%;
    border-radius: 50%;
  }

  body {
    background:#c6faf1;
  }

  .penguin * {
    position: absolute;
  }
</style>
<div class="penguin">
  <div class="penguin-bottom">
    <div class="right-hand"></div>
    <div class="left-hand"></div>
    <div class="right-feet"></div>
    <div class="left-feet"></div>
  </div>
  <div class="penguin-top">
    <div class="right-cheek"></div>
    <div class="left-cheek"></div>
    <div class="belly"></div>
    <div class="right-eye">
      <div class="sparkle"></div>
    </div>
    <div class="left-eye">
      <div class="sparkle"></div>
    </div>
    <div class="blush-right"></div>
    <div class="blush-left"></div>
    <div class="beak-top"></div>
    <div class="beak-bottom"></div>
  </div>
</div>
```
</details>
<hr />
<hr />
