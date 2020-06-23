# SummerPractice

Репозиторий для летней практики 2020

### Команда
* Крыжановский Кирилл, гр. 8303
* Кибардин Антон, гр. 8303
* Спирин Никита, гр. 8303

***


Разработка будет поэтапной, поэтому нужно сделать fork данного репозитория. 
* Делаем pull-request и описание к нему на _русском_ языке (чтобы нам легче понимать друг друга). 
* Commit'ы делать осмысленными. Чтобы не было что-то вроде _fix_, _some fixes_, и другое
* Будем стараться работать с [Issues](https://github.com/thehighestmath/SummerPractice/issues) (надпись кликабельная). Это такой механизм в котором мы можем указывать, что в коде не так, какой баг найден, что доработать и т.д. Создание issue __не__ меняет содержимое репозитория, в отличие от pull-request'а

***

## Задание -- визуализировать алгоритм Краскала

Об алгоритме можно посмотреть [тут](https://ru.wikipedia.org/wiki/%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC_%D0%9A%D1%80%D0%B0%D1%81%D0%BA%D0%B0%D0%BB%D0%B0) или ниже


***

[Источник](https://github.com/Nik-Poch/EducationProjects/blob/master/%D0%9F%D0%90%D0%90/Theory/%D0%93%D1%80%D0%B0%D1%84%D1%8B/%D0%9E%D1%81%D1%82%D0%BE%D0%B2%D0%BD%D1%8B%D0%B5%20%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D1%8C%D1%8F.md#%D0%B6%D0%B0%D0%B4%D0%BD%D1%8B%D0%B9-%D0%B0%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC-%D0%BA%D1%80%D0%B0%D1%81%D0%BA%D0%B0%D0%BB%D0%B0)

## Теория

__Жадный алгоритм__ - на каждом шаге делается лучшая для данного момента операция.

Идея алгоритма в следующем - в множество __E'__ остовного дерева __G' = (V, E')__ графа __G = (V, E)__ в порядке невозростания весов добавляются рёбра.

- Если очередное ребро соединяет вершины одной компоненты связности __G'__, то добавление его создаст цикл.

- Если же оно соединяет вершины разных компонент, то по теореме о минимальном ребре оно безопасно и может быть включено в граф.

### Псевдокод

```
G = (V, E)      // исходный граф
G' = (V', E')   // результат алгоритма
V' ← V
E' ← ∅
for (uv ∈ E ordered by w(u,v))
	if (Component(u) ≠ Component(v))
        E' ← uv
```

### Пример

> В кружках около вершины - номер шага

![Жадный алгоритм (Краскала)](./_resources/graph.png)

_Визуализация алгоритма_

![Жадный алгоритм (Краскала)](./_resources/visual.gif)
