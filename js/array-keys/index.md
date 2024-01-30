---
title: "`.keys()`"
description: "Возвращает объект-итератор индексов элементов массива."
authors:
  - vitya-ne
related:
  - js/arrays
  - js/iterator
  - js/values
tags:
  - doka
---

## Кратко

Метод `keys()` возвращает новый объект-итератор, созданный из индексов всех элементов массива. Подробнее о том, что такое итератор, можно прочитать в статье [Итератор](/js/iterator/).

## Пример

Создадим объект-итератор и получим его значения с помощью `for...of`:

```js
const chords = ['Am', 'G', 'C', 'Em7']

const iterator = chords.keys()

for (const item of iterator) {
  console.log(item)
}

// 0
// 1
// 2
// 3
```

## Как пишется

`Array.keys()` не имеет аргументов.

`Array.keys()` возвращает новый объект-итератор, реализующий протокол перебора массива. При переборе для каждого элемента коллекции возвращается индекс элемента в исходном массиве.

## Как понять

Метод `keys()` работает схожим образом с методом `values()`, но позволяет получить для каждого элемента его индекс.

`Array.keys()` не нужно путать со статическим методом `Object.keys()`, который возвращает массив индексов перечисляемых свойств объекта.

## Подсказки

💡 Oбъект-итератор, созданный при вызове `keys()`, вернёт при обходе индекс для всех элементов массива, включая незаполненные элементы:

```js
const cities = []
cities[2] = 'Лондон'

console.log(item)
// [ <2 empty items>, 'Лондон' ]

const iterator = cities.keys()

for (const item of iterator) {
  console.log(item)
}
// 0
// 1
// 2
```