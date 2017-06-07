В этом репозитории находится Jekyller - генератор разметки для [Shower](https://github.com/shower/shower) на основе контента в md. Также здесь подключена тема оформления слайдов с корпоративным стилем Яндекса.

- [Установка](#Установка)
- [Использование](#Использование)
  - [Добавление слайдов](#Добавление-слайдов)
  - [CSS классы](#css-классы)
  - [Изображения](#Изображения)
  - [Постепенное появление элементов слайда](#Постепенное-появление-элементов-слайда)
  - [Размеры и позиционирование](#Размеры-и-позиционирование)
- [Дополнительно](#Дополнительно)
  - [Как сконвертировать в PDF](#Как-сконвертировать-в-pdf)
  - [Материалы для презентаций](#Материалы-для-презентаций)
  - [Контакты](#Контакты)

## Установка

Jekyll Shower работает в GitHub Pages и для его использования не нужно ничего устанавливать на свой компьютер.

-  Форкните [этот репозиторий](https://github.yandex-team.ru/presentation/jekyller)
-  Внесите необходимые изменения (например укажите информацию о презентации и добавьте свой контент для слайдов). Кстати, это можно делать через web-интерфейс GitHub.
-  Сделайте Commit и Push своих изменений. GitHub автоматически запустит генерацию слайдов и через несколько минут презентация будет доступна на GitHub Pages по адресу: [https://github.yandex-team.ru/pages/<ваш-логин>/jekyller](https://github.yandex-team.ru/pages/presentation/jekyller).

Обратите внимание, генерация слайдов запускается при выполнении операции Push (например, это значит, что в первый раз слайды будут сгенерированы при первой операции Push, а не при создании форка репозитория).

## Использование

Делать презентации с использованием Shower очень просто. Всё, что вам нужно - указать информацию о презентации в файле [_config.yml](_config.yml) и добавить свой контент в файл [index.md](index.md).

В файле `_config.yml` вы можете указать название и авторов презентации, выбрать соотношение сторон для слайдов (доступны варианты `4x3`, `16x9`, `16x10`) и язык для отображения логотипа Яндекса (`ru`, `en`).

В файле `index.md` находится содержимое, на основе которого будут сгенерированы слайды. По умолчанию там находится контент-заглушка, иллюстрирующий оформление слайдов разных типов. Используйте его в качестве примера. Также обращайте внимание на пояснения в комментариях.

### Добавление слайдов

Для добавления в преентацию нового слайда опишите заголовок второго уровня (текст заголовка будет использоваться как заголовок слайда).

```md
## Название слайда
```

### CSS классы

Вы можете назначать элементам презентации произвольные css классы. Для этого на следующей строке после элемента укажите название класса следующим образом:

```md
<!-- картинка справа-->
![](themes/yandex2/images/image-right.svg)
{:.image-right}
```

Можно указать несколько классов через пробел.

```md
## Название слайда
{:.images .two}
```

В теме оформления уже определено несколько классов, которые можно использовать для оформления слайдов. Смотрите примеры в файле `index.md`. Описать собственные css классы можно в специальном разделе начале файла `index.md`.

### Изображения

Если необходимо сделать слайд с изображениеми, используйте один из примеров в файле `index.md`. Старайтесь, чтобы размеры изображений соответствовали размерам, указанным на изображениях-заглушках в примерах.

Вы можете использовать пиктограммы - небольшие схематические изображения размером 240x200px. Библиотека пиктограмм находится по адресу https://patterns.yandex-team.ru/presentations?typeIn=icons. В файле `index.md` есть несколько примеров слайдов с пиктограммами (они отмечены классом `icons`).

Также вы можете выбрать фотографию на фотостоке [istockphoto.com](http://www.istockphoto.com/ru) и прислать нам ссылку, мы купим её для вас.


### Постепенное появление элементов слайда

Иногда необходимо, чтобы элемнеты слайда появлялись постепенно. Например, может потребоваться поочередное появление на слайде элементов списка. Используйте для этого css класс `next`. Отмеченные им элементы будут появляться по очереди в порядке следования в md файле. Например:

```md
![](image-1.svg)
{:.next}

![](image-2.svg)
{:.next}

![](image-3.svg)
{:.next}
```

Пример списка, элементы которого появляются по очрееди:

```md
1. {:.next}Нумерованный список
2. {:.next}Нумерованный список
3. {:.next}Нумерованный список
```

### Размеры и позиционирование

Если необходимо задать размеры для элементов, указывайте значения в пикселях. При масштабировании слайдов элементы будут масштабироваться автоматически. Ширина слайда равна 1920px.

Если нужно разместить элемент в нестандартном месте (например, прижать к правому или нижнему краю слайда), используйте абсолютное позиционирование. 

По умолчанию стили для слайдов написаны так, чтобы контент был выровнен по сетке с шагом 30px. При выборе размеров и положения элементов старайтесь, чтобы они тоже соответствовали сетке. Чтобы включить отображение сетки на слайде, добавьте для него css класс `grid`.

```md
## Название слайда
{:.grid}
```

## Дополнительно

### Как сконвертировать в PDF

Чтобы получить презентацию в формате PDF, откройте ее в любом chromium-браузере и в режиме списка слайдов распечатайте её, выбрав в качестве принтера "Сохранение в PDF".

### Материалы для презентаций

Материалы для презентаций (примеры оформления слайдов с графиками, диаграммами, таблицами, картами, схемами, гаджетами, пиктограммы, иллюстрации и фотографии) находятся по адресу https://patterns.yandex-team.ru/presentations.

### Контакты

Если возникли вопросы, пишите на рассылку [presentation@](presentation@yandex-team.ru). Если вы хотите, чтобы мы проверили вашу презентацию, отправьте её на [prescheck@](prescheck@yandex-team.ru).
