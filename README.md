Нам необходимо решить антагонистическую матричную игру.
**Игрой** с математической точки зрения называется тройка <X, Y, F(x, y)>, где X = {X1, ..., Xn} и Y = {Y1, ..., Yn} --- множества стратегий первого и второго игроков соотвественно, а F(x,y) - это **функция выигрыша**. Матрица, в которой строки соответсвуют стратегиям игрока X, а столбцы --- стратегиям игрока Y, элементами a(i, j) которой являются результаты игры при i-й стратегии игрока X и j-й стратегии игрока Y, называется **матрицей выигрышей**. Матричная игра называется **антагонистической**, если в ней участвуют два игрока и значения функций выигрыша в каждой ситуации равны по величине, но противоположны по знаку  (весь проигрыш одного игрока является выигрышем другого). Нужно найти значение игры и оптимальные стратегии первого и второго игроков при заданной матрице.
# Ход решения

**Чистая стратегия** - возможный ход игрока, выбранный с вероятностью 1. Для каждого игрока возникает вопрос увеличения выигрыша (уменьшения проигрыша). Это можно сделать применяя **смешанные стратегии** - вероятностное распределение на множестве X для первого игрока (Y - для второго). 

 1.  Не ограничивая общности, приведем матрицу к удобному виду: если в ней есть  отрицательные элементы, то прибавив модуль наименьшего элемента матрицы мы получаем неотрицательную матрицу. Тогда мы можем сказать, что **цена игры** положительна: v > 0. 
 2. Прежде чем сводить исходную задачи к двойственной задаче линейного программирования (ЗЛП), пробуем найти решение в чистых стратегиях. Это подразумевает нахождение в матрице выигрышей седловой точки. **Седловой точкой** матрицы `а(i,j)` размера *m * n* называется такая пара (i<sub>0</sub>,j<sub>0</sub>), что для любых i=1, ..., n и j=1, ...,n выполнено a(i,j<sub>0</sub>)<= a(i<sub>0</sub>,j<sub>0</sub>) <= a(i<sub>0</sub>,j). То есть, для каждой строки мы находим свой минимум (min), а затем выбираем максимум среди найденных значений (maxmin), а для каждого столбца --- максимум (max), а затем выбираем минимум из этих значений (minmax). Если maxmin = minmax = M, то цена игры равна a<sub>ij</sub>, и первый игрок выбирает стратегию i, а второй игрок стратегию j. Если матрица игры A не имеет седловой точки, то
