# Билет 1
## Компоненты сильной связности
![Screenshot](../algo_data/ticket_1_1.png)

# Билет 2
- Эйлеров цикл - цикл, содержащий все ребра графа 
- Граф эйлеров, если все вершины графа имеют четную степень, если же граф ориентированный, то его эйлеровость определяется равенством входящих и исходящих ребер каждой вершины

![Доказательство](../algo_data/ticket_2_1.png)

## Построение Эйлерова цикла


![Построение](../algo_data/ticket_2_2.png)


- Для ориентированного случая делаем 
все то же самое, только теперь ребра не нужно удалять, все хранить можно в ```vector<vector<Edge>>```# Билет 3
##  Определения
- Ребро (a, b) называется **мостом**, если после его удаления a и b не связны.
- **Точка сочленения** – вершина, при удалении которой увеличивается число ком- понент связности.
## Мосты
- Замечание:  После удаления из графа мостов, компоненты связности и рёберной двусвязности будут совпадать. Доказательство: ((𝑎, 𝑏) – не мост) ⇔ (𝑎 и 𝑏 рёберно двусвязны).
### Алгоритмы поиска мостов


![Алгоритмы поиска мостов](../algo_data/ticket_3_1.png)
## Точки сочленения 

- Замечание: точки сочленения – ровно те вершины, у которых есть смежные рёбра из разных компонент вершинной двусвязности.
- Два ребра называют **вершинно двусвязными**, если существуют вершинно непересекающиеся пути, соединяющие их концы.

### Алгоритмы поиска

![Алгоритмы поиска точек сочленения](../algo_data/ticket_3_2.png)

- Доказательство корректности, которого почему-то нет в конспекте:


![Доказательство](../algo_data/ticket_3_3.png)



# Билет 4
## Двусвязность определения через отношение эквивалентности
### Реберная
![Определение и теорема](../algo_data/ticket_4_1.png)
### Вершинная
![Определение и теорема](../algo_data/ticket_4_2.png)
## Алгоритм поска компонент вершинной двусвязности 
![Алгоритмы поиска точек сочленения](../algo_data/ticket_3_2.png)

# Билет 5
## 2-SAT
![2 list clolring](../algo_data/ticket_5_1.png)
- Тут необходимо пояснение: ```pos[a][c]``` - это индекс цвета ```c``` в списке ```l``` вершины ```a```
![2 list clolring](../algo_data/ticket_5_2.png)

## Решение 2-SAT
![2 list clolring](../algo_data/ticket_5_3.png)
# Билет 6
## Неразрешимость Halting Problem
- Halting Problem - "Дана программа, остановится ли она когда-нибудь на данном входе?"
![Теорема](../algo_data/ticket_6_1.png)
## Понятие Decision, Search задачи, языка
![Задачи](../algo_data/ticket_6_2.png)
## Определения DTime, P, EXP

![Определения](../algo_data/ticket_6_3.png)

### Более простым языком:
- **DTime(f(n))** - называется множество языков, для которых существует машина Тьюринга такая, что она всегда останавливается, и время ее работы не превосходит f(n), где n — длина входа.
- **P** - множество задач, для которых существуют полиномиальные алгоритмы решения.
- **EXP** - множество задач, сложность которых ограничена экспонентой от полинома от размерности задачи, то есть ограничена функцией exp(P(n)), где P - некоторый многочлен, а n - размер задачи.

## Cледствие P != EXP из теоремы об иерархии по времени

![Теорема](../algo_data/ticket_6_4.png)
## Билет 25
Автор: Габитов Даниил.

### Поиск в ширину. Решение очередью

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_25_1.jpg" alt="."/>
</p>

### Вещественный 0-1 BFS
* Решение с пракики.
<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_25_2.jpg" alt="."/>
</p>

### Структура кратчайших путей

Необходимо понимание стркутуры, в частности, что BFS строит дерево.
// I do not know what to say beside that
## Билет 26
Автор: Габитов Даниил.

### Решение для 0-k BFS

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_1.png" "width = 800" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_2.png" alt="home"/>
</p>

* Так же есть более подробное [описание основ](https://wiki.algocode.ru/index.php?title=0-K_BFS) алгоритма

### 0-1 BFS на деке

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_3.png" alt="home"/>
</p>
## Билет 27
Автор: Габитов Даниил

### Матрица расстояний

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_27_1.png" alt="home"/>
</p>

# Comment on solution

Как будем перебирать единицы в current? Можем найти минимальный бит у числа за единицу: x & -x. Давайте перебирать все числа(!) в битсете. Если число ноль - пропускаем, иначе у числа нужно взять минимальный бит, пока берется, занулять его и запоминать, что это за вершина была. Ассимптотика верная: Перебираем все числа за O(V / w), берем минимум O(n_{d}) раз. 

### 1-k bfs

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_27_2.png" alt="home"/>
</p>

## Билет 28
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_28_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_28_2.png" alt="home"/>
</p>
## Билет 29
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_29_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_29_2.png" alt="home"/>
</p>
## Билет 30
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_30_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_30_2.png" alt="home"/>
</p>
## Билет 31
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_31_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_31_2.png" alt="home"/>
</p>

* Подробнее про [транзитивное замыкание](https://neerc.ifmo.ru/wiki/index.php?title=%D0%A2%D1%80%D0%B0%D0%BD%D0%B7%D0%B8%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B5_%D0%B7%D0%B0%D0%BC%D1%8B%D0%BA%D0%B0%D0%BD%D0%B8%D0%B5)

* Идея для обычного Флойда должна быть тривиальна. Чтобы понять, почему переход на битсет так работает, помогает нарисовать табличку и вспомнить определение транзитивности.
## Билет 32
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_3.png" alt="home"/>
</p>
## Билет 33
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_33_1.png" alt="home"/>
</p>


* Алгоритм восстановления == просто обратные ссылки?
## Билет 34
Автор: Габитов Даниил



<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_3.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_4.png" alt="home"/>
</p>
## Билет 35
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_35_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_35_2.png" alt="home"/>
</p>
## Билет 36
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_36_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_36_2.png" alt="home"/>
</p>
## Билет 37
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_37_1.png" alt="home"/>
</p>
## Билет 38
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_38_1.png" alt="home"/>
</p>



<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_38_2.png" alt="home"/>
</p>
## Билет 39
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_39_1.png" alt="home"/>
</p
## Билет 45
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_4.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_5.png" alt="home"/>
</p>

[Статья по приближениям](http://www.cs.tufts.edu/~cowen/advanced/2002/adv-lect3.pdf)

[Ссылка на лекцию CSS](http://www.cs.tufts.edu/~cowen/advanced/2002/adv-lect3.pdf)

### Правило Варнсдорфа.

В конспекте ничего нет. Есть только [определение](https://ru.wikipedia.org/wiki/%D0%97%D0%B0%D0%B4%D0%B0%D1%87%D0%B0_%D0%BE_%D1%85%D0%BE%D0%B4%D0%B5_%D0%BA%D0%BE%D0%BD%D1%8F) на вики
## Билет 46
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_46_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_46_2.png" alt="home"/>
</p>
## Билет 47
Автор: Даниил Габитов
// TODO спросить на консультации. Непонятно что хотят услышать.
## Билет 48
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_48.png" alt="home"/>
</p>
## Билет 49
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_49.png" alt="home"/>
</p>
## Билет 58


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_4.png" alt="home"/>
</p>