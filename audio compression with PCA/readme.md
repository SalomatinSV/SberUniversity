# Сжатие звуковой дорожки при помощи РСА

## Описание проекта

Предоставлена звуковая дорожка, нужно провести исследование её сжатия при помощи РСА

## Навыки и инструменты

- **numpy**
- **scipy**
- **matplotlib**
- **Psklearn.decomposition.CA**

## Цель исследования

- Количество компонент, которое вы выбрали это много или мало?
- Как сильно можно сжать звук таким образом?
- А если нам дадут другую звуковую дорожку, нам надо сделать то же самое, чтобы сжать звук, как автоматически подобрать число компонент и возможно ли это?
- Проведите исследование того, как степень сжатия влияет на звук, по субъективным ощущениям. Начиная с какой степени сжания сильно слышится потеря качества? (как с учетом фильтрации с помощью gaussian_filter1d, так и без неё)
- Можно ли как-то автоматически подобрать степерь сжатия? За что она отвечает в нашей задаче. Как степень сжатия влияет на звук? Почему она так влияет на звук?
- Что степень сжатия означает для PCA? Для большой аудиозаписи (3 мин, например) мы хотели бы разбить на большее, меньшее или такое же число отрезков как и для предложенной аудиозаписи? Почему?

## Ход исследования

1) Разделите сигнал на равные части (длину каждой части возьмите равной 1000) и соберите из них "датасет", который будет представлять из себя двухменый массив - "матрицу", в которой каждая часть сигнала длины 1000 находится в отдельной строке).
2) Напишите функцию, которая будет переводить вашу "матрицу" обратно в звуковой сигнал, то есть разворачивать данные обратно из матрицы размера (число объектов, 1000) в вектор длины (число объектов * 1000)
3) Выполните PCA преобразование нашей матрицы, и получите данные, сжатые в пространство меньшей размерности.
4) Постройте сами две главные компоненты в наглядной форме. 
5) Постройте scatter plot датасета в пространстве первых двух компонент, а третью используйте как цвет.
6) Выполните обратное PCA преобразование сжатых данных и получите "матрицу" с сжатым звуком.
7) Преобразуйте "матрицу", получившуюся обратным преобразованием, в сигнал (одномерный массив, наш "сжатый" монозвук), и послушайте результат
8) Исследуйте зависимость качества звука от числа компонент. Подберите "на слух" минимальное число компонент, при котором звук практически не отличается от оригинала.


