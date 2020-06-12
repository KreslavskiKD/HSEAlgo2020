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