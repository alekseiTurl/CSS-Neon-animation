# CSS-Neon-animation
*Посмотреть демо [на Codepen](https://codepen.io/AlexTur/pen/eYxMPjg)*

Стиль Neon CSS создает неоновый эффект для элементов HTML. Он использует комбинацию фоновых градиентов, анимаций и псевдоэлементов для достижения желаемого эффекта. Он может быть использован для создания привлекательных и заметных дизайнов на вашем веб-сайте. Не стесняйтесь экспериментировать с настройками и адаптировать его под свои потребности

## Использование
Для использования стиля Neon CSS следуйте этим шагам:

Включите CSS-код в свой проект. Вы можете добавить его непосредственно в ваш файл HTML или включить его в ваш внешний файл CSS.

Примените класс `.neon` к элементу HTML, к которому вы хотите применить неоновый эффект.

```html
<div class="neon"></div>
```

**CSS-код**

```css
.neon {
    position: relative;
    background: repeating-conic-gradient( from var(--extent),#ff2770 0%, #ff2770 5%, transparent 5%, transparent 40%, #ff2770 50%);
    animation: neon 4s linear infinite;
    border-radius: 20px;
}

.neon::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: repeating-conic-gradient( from var(--extent),#45f3ff 0%, #45f3ff 5%, transparent 5%, transparent 40%, #45f3ff 50%);
    animation: neon 4s linear infinite;
    animation-delay: -1s;
    border-radius: 20px;
}

.neon::after {
    content: '';
    position: absolute;
    inset: 3px;
    background: #222;
    border-radius: 20px;
    border: 8px solid #222;
}

@property --extent {
    syntax: '<angle>';
    inherits: false;
    initial-value: 0deg;
}

@keyframes neon {
    0% {
        --extent: 0deg;
    }
    100% {
        --extent: 360deg;
    }
}
```

## CSS-классы

* `.neon` : Применяется к элементу HTML для создания неонового эффекта.

## CSS-свойства
 
* `background` : Устанавливает фоновый градиент с помощью функции repeating-conic-gradient.
* `animation` : Применяет анимацию neon для создания анимированного эффекта.
* `border-radius` : Задает радиус скругления границы для создания закругленных углов.
* `animation-delay` : Задержка анимации псевдоэлемента

## Настройка
Вы можете настроить эффект Neon, изменяя CSS-код. Вот несколько вариантов настройки:

- Измените продолжительность анимации, модифицируя свойство `animation` в классе ***.neon***
- Измените цвета и градиенты, используемые в свойстве `background` , чтобы изменить неоновый эффект.
- Измените размер и форму элемента, модифицируя свойство `border-radius`
- Измените задержку анимации псевдоэлемента `::before` , модифицируя свойство `animation-delay`
- Модифицируйте свойства границы в псевдоэлементе `::after` , чтобы изменить эффект рамки.

## Поддержка браузерами
Стиль Neon CSS зависит от свойства `backdrop-filter` , которое не поддерживается всеми браузерами. Убедитесь, что целевые браузеры поддерживают это свойство или предоставьте альтернативные стили для браузеров, которые его не поддерживают.
