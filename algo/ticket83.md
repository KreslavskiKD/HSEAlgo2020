## Билет 83
Автор: Габитов Даниил

### K-ая порядковая статистика.

* За log^3 бинпоиск + 2D ДО

* За log^2 заменяем 2D ДО на разницу преффиксов. Для этого поддерживаем персистентное дерево отрезков по значению.

* За log заметим, что строение двух версий деревьев не отличается по строению, значит, можно одно вычесть из другого и получить отрезок [l, r]. Тогда бинпоиск можно заменить на 1 спуск. Спускаясь ищем минимальное значение >= k.

##### [Ссылка на лекцию](https://youtu.be/d9fBIjjOcaI?t=624)