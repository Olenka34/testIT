1. Какими способами можно подключать CSS-стили? Найдите сами еще один способ, не указанный в уроке

1) Встроенные стили (Inline) — использование атрибута style в самом теге HTML.
<div style="color:blue; font-size:14px;">Текст.</div>
Использование встроенных стилей обычно считается плохой практикой. Поскольку стили смешиваются с разметкой документа, это делает код сложным для поддержки.
2) Внедренные стили (Embed) — использование элемента <style> в разделе <head> документа.
   Встроенные или внутренние таблицы стилей влияют только на текущий документ, в который они встроены.
   Встроенные таблицы стилей должны быть определены в <head> разделе документа HTML с использованием элемента <style> . Можно определить любое количество элементов <style> в документе HTML, но они должны появляться между тегами <head> и </head>.
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <title>Пример HTML Документа</title>
       <style>
           body { background-color: yellow; }
           p { color: #fff; }
       </style>
   </head>
   <body>
       <h1>Это заголовок</h1>
       <p>Это параграф текста.</p>
   </body>
   </html>

3) Внешние стили (External) — с помощью элемента <link> указывающего на внешний файл CSS.
   Внешние таблицы стилей идеально подходят, когда их нужно применить ко многим страницам веб-сайта. Внешняя таблица стилей содержит все правила в отдельном документе, на который вы можете ссылаться из любого HTML-файла на своем сайте. Внешние таблицы стилей являются наиболее гибкими, поскольку с помощью внешней таблицы изменив только один файл можно изменить внешний вид всего веб-сайта.
   Перед установкой ссылки нам нужно сначала создать таблицу стилей. Нужно создать новый файл, затем ввести следующий CSS-код внутри этого файла и сохранить файл как "style.css".
   body {
   background: lightyellow;
   font: 18px Arial, sans-serif;
   }
   h1 {
   color: orange;
   }
   Внешняя таблица стилей может быть связана с HTML-документом с помощью тега <link>. Тег <link> должен находится внутри раздела <head:
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <title>Мой HTML-документ</title>
       <link rel="stylesheet" href="css/style.css?utm_source=artzolin.ru">
   </head>
   <body>
       <h1>Это заголовок</h1>
       <p>Это параграф текста.</p>
   </body>
   </html>
   Среди всех трех методов использование внешней таблицы стилей является лучшим методом определения и применения стилей к HTML-документам. При их использовании, исходный HTML-файл требует минимальных изменений в разметке.
4) Прикрепление стилей с помощью @import
   Правило @import — это еще один способ загрузки внешней таблицы стилей. Оператор @import указывает браузеру загрузить внешнюю таблицу стилей и использовать ее.
   Самый простой способ использования — в заголовке (<head>) документа. Обратите внимание, что другие правила CSS все еще могут быть включены в элемент <style> . Вот пример:
   <style>
       @import url("css/style.css?utm_source=artzolin.ru");
       p {
           color: blue;
           font-size: 16px;
       }
   </style>
   Точно так же можно использовать правило @import для импорта таблицы стилей внутри другой таблицы.

@import url("css/layout.css");
@import url("css/color.css");
body {
color: blue;
font-size: 14px;
}
Все правила @import должны появляться в начале таблицы стилей. Любое правило, определенное в самой таблице стилей, переопределяет конфликтующие правила в импортированных таблицах стилей. Однако импортировать таблицу стилей в другую таблицу стилей не рекомендуется из-за проблем с производительностью. 2. Зачем нужен Normalize.css?
Normalize.css — это небольшой CSS-файл, который обеспечивает для HTML-элементов лучшую кроссбраузерность (поддержку разных браузеров) в стилях по умолчанию.
Цели normalize.css:

- сохранять полезные настройки браузера, а не стирать их
- нормализовать стили для широкого круга HTML-элементов
- корректировать ошибки и основные несоответствия браузера
- совершенствовать юзабилити незаметными улучшениями
- объяснять код, используя комментарии и детальную документацию

3. Что такое CSS-директивы?
4. В чем разница между **margin** и **padding**?
   Padding — внутренний отступ, внутреннее пространство между содержимым элемента и его границей border.
   margin — внешний отступ, пространство от border
5. Как в CSS определяются приоритеты? Какое из свойств будет приоритетнее - `#link .main` или `span #login`?
   #link .main будет приоритетней
   id всегда приоритетней чем тег
6. В чем разница между CSS1 и CSS3?
   Главное различие между CSS и CSS3 состоит в том, что CSS — это простой язык дизайна, который позволяет создавать привлекательные веб-страницы, тогда как CSS3 — это последняя третья версия языка каскадных таблиц стилей, имеющая новые функции, позволяющие работать с веб-дизайном намного более эффективно. CSS3 содержит множество новых функций и дополнений, таких как расширенные селекторы, закругленные углы, новые макеты, анимация или переходы, тени, градиенты, выбор цвета и многое другое.
7. Что такое псевдоклассы? А псевдоэлементы?
   Псевдоклассы определяют динамическое состояние элементов, которое изменяется с помощью действий пользователя, а также положение в дереве документа. Примером такого состояния служит текстовая ссылка, которая меняет свой цвет при наведении на неё курсора мыши. При использовании псевдоклассов браузер не перегружает текущий документ, поэтому с помощью псевдоклассов можно получить разные динамические эффекты на странице.
   Синтаксис применения псевдоклассов :
   селектор:псевдокласс { ... }
   Вначале указывается селектор, к которому добавляется псевдокласс, затем следует двоеточие, после которого идёт имя псевдокласса. Допускается применять псевдоклассы к именам идентификаторов или классов (`a.menu:hover {color: green}`), а также к контекстным селекторам (`.menu A:hover {background: #ffcc00}`). Если псевдокласс указывается без селектора впереди (`:hover`), то он будет применяться ко всем элементам документа.
   Примеры псевдоклассов:

- определяющие состояние элементов
- имеющие отношение к дереву элементов
- использующиеся для работы с формами
  Псевдоэлементы создают "виртуальные теги" и позволяют стилизовать их.
  Синтаксис использования псевдоэлементов:
  селектор::псевдоэлемент { ... }
  Каждый псевдоэлемент может применяться только к одному селектору, если требуется установить сразу несколько псевдоэлементов для одного селектора, правила стиля должны добавляться к ним по отдельности.
  .foo::first-letter { color: red; }
  .foo::first-line { font-style: italic; }

8.  Изучите статью про "плохие" теги [https://msiter.ru/tutorials/html-srednego-urovnya/plokhie-tegi](https://msiter.ru/tutorials/html-srednego-urovnya/plokhie-tegi) и пришлите список тегов, которые нежелательно использовать
<b>
<i>
<big>
<small>
<hr>
<u>
<center>
<layer>
<blink> или <marquee>
<font>
9.  Как можно подключать шрифты локально?
    Для реализации используют CSS-правило @font-face.
    Одинаковые шрифты подключаются с одним именем, различающуюся жирность и стиль пишут в font-weight и font-style.
    Для современных браузеров нужны форматы woff2 и woff. Вначале указывается путь к файлу woff2, затем к woff. Таким образом, если браузер умеет работать с более современным форматом шрифтов, то он применит его. Если нет, то возьмет формат woff.
    @font-face {
    font-family: "OpenSans";
    src: url("fonts/opensans.woff2") format("woff2"),
    url("fonts/opensans.woff") format("woff");
    font-weight: normal;
    font-style: normal;
    font-display: swap;
    }

            @font-face {
            font-family: "OpenSans";
            src: url("fonts/opensansbold.woff2") format("woff2"),
            url("fonts/opensansbold.woff") format("woff");
            font-weight: 700;
            font-style: normal;
            font-display: swap;
            }

    Теперь этот шрифт можно применять к нужным блокам. Для разной жирности или начертания браузер будет подтягивать нужные файлы для правильного отображения.
    div {
    font-family: OpenSans, Arial, sans-serif;
    font-weight: bold;
    }
    Обязательно нужно указать запасной веб-безопасный шрифт и семейство.

10. Почему не стоит использовать сокращенную запись без необходимости? И если все же использовать, как это делать правильно?
    Применение этих свойств сокращает объём кода и повышает его читабельность, но с другой стороны иногда добавляет путаницу. Чтобы избежать проблем, следует, во-первых, группировать свойства по смыслу, это позволит быстрее находить ошибки, а во-вторых, если нужно переопределить значения ранее заданных свойств, не использовать сокращённую запись.
11. Разберитесь самостоятельно, как сделать анимацию через CSS
    CSS-анимации состоят из двух компонентов:

- стилевое описание анимации
- набор ключевых кадров, определяющих начальное, конечное и, возможно, промежуточное состояние анимируемых стилей.
  Делаем это с помощью двух свойств:
- **`@keyframes`** – задаем внешний вид анимации
- `**animation`\*\* – задаем КАК должна протекать анимация (продолжительность, ускорение и т.д.)

# testIT
