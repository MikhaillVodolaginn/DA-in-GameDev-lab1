# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил:
- Водолагин Михаил Алексеевич
- РИ210942
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Ознакомиться с основными операторами языка Python на примере реализации линейной регрессии.

## Задание 1
- Hello, world в google colab
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.18.41.png?raw=true)

- Hello, world в unity
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2022.07.22.png?raw=true)

## Задание 2
- Подготовка данных для работы с алгоритмом линейной регрессии. 10 видов данных были установлены случайным образом, и данные находились в линейной зависимости. Данные преобразуются в формат массива, чтобы их можно было вычислить напрямую при использовании умножения и сложения.
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.26.27.png?raw=true)

- Определение связанных функций. Функция модели: определяет модель линейной регрессии wx + b. Функция потерь: функция потерь среднеквадратичной ошибки. Функция оптимизации: метод градиентного спуска для нахождения частных производных w и b.
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.32.50.png?raw=true)

- Инициализация и модель итеративной оптимизации
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.39.09.png?raw=true)

- 2 итерации
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.44.32.png?raw=true)

- 3 итерации
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.46.50.png?raw=true)

- 4 итерации
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.47.09.png?raw=true)

- 5 итераций
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2016.49.05.png?raw=true)

- 10000 итераций
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2017.08.40.png?raw=true)

## Задание 3
### Должна ли величина loss стремиться к нулю при изменении исходных данных?

- Величина loss является среднеквадратичной ошибкой. Она будет тем меньше, чем ближе расположение точек к прямой с заданными коэффициентами, и будет стремиться к нулю, если точки будут лежать на одной прямой.
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2022.15.22.png?raw=true)

### Какова роль параметра Lr?

- Параметр Lr отвечает за скорость обучения программы. Чем меньше Lr, тем меньше необходимо пройти итераций для получения результата с близкой к 0 loss.
[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2017.08.40.png?raw=true)

[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2022.45.23.png?raw=true)

[![](https://github.com/MikhaillVodolaginn/DA-in-GameDev-lab1/blob/main/Снимок%20экрана%202022-09-28%20в%2022.51.42.png?raw=true)

## Выводы

В данной лабораторной работе я запустил свой первый проект на unity, а так же впервые проанализировал линейную регрессию, узнав тем самым принцип ее работы.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

Vodolagin Mikhail
