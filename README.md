# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил:
- Карабанов Павел Александрович
- РИ210942
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:


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
познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.

## Задание 1. Написать программы Hello World на Python и Unity.
#### -Реализовать систему машинного обучения в связке Python - Google-Sheets – Unity. При выполнении задания можно использовать видео-материалы и исходные данные, предоставленные преподавателями курса.

### Ход работы:

**Установка необходимых пакетов.

![image](https://user-images.githubusercontent.com/104727697/198155577-be21425d-c124-46d7-ae7d-87c0dcae629c.png)

**Создание 3 объектов, присвоение им материала, добавление rigidbody и скрипта к шару.**

![Lab3 1 2](https://user-images.githubusercontent.com/104727697/198154792-13fd3f0f-7655-4269-8009-9c65e85a7d97.png)
![image](https://user-images.githubusercontent.com/104727697/198155651-cf9bb20b-e3a1-4c7a-8a21-15f0739e703c.png)


**Запустк обучения MLAgent в конфигурации rollerball_config.yaml на 3,9,27 копиях ранее созданного Prefab.**

`mlagents-learn rollerball_config.yaml --run-id=RollerBall --force`

![Lab3 1 3](https://user-images.githubusercontent.com/104727697/198154798-267a36d0-762a-421d-9048-cba17325b5fa.png)
![Lab3 1 4](https://user-images.githubusercontent.com/104727697/198154800-0ca20604-1ecf-4ee1-a285-d3ccbe349dd3.png)
![Lab3 1 5](https://user-images.githubusercontent.com/104727697/198154804-dc19e373-f17b-4f71-85ed-ce4f2c2f28b5.png)

**Полученные по итогу обучения результаты**
![Train1](https://user-images.githubusercontent.com/104727697/198154795-0f1910d9-7a92-4196-8cce-c697b049646e.png)

----
## Задание 2
### Подробно опишите каждую строку файла конфигурации нейронной сети, доступного в папке с файлами проекта по ссылке. Самостоятельно найдите информацию о компонентах Decision Requester, Behavior Parameters, добавленных на сфере.
```

behaviors:
#Основной раздел файла конфигурации тренера — это набор конфигураций для каждого поведения в сцене.

RollerBall:
#Название нашей конфигурации.

trainer_type: ppo 
# Сам параметр отвечает за тип используемого тренера (по умолчанию ppo). Это совокупность алгоритмов обучения, довольно простых в применении, но почти не уступающих аналагам.

hyperparameters 
# Это раздел настройки гиперпараметров для агента.

batch_size 
# Количество опыта на каждой итерации градиентного спуска.

buffer_size 
# Количество опытов, которые необходимо собрать перед обновлением модели политики. Обычно большее buffer_size значение соответствует более стабильным обновлениям обучения.

learning_rate 
# Начальная скорость обучения для градиентного спуска. Соответствует силе каждого шага обновления градиентного спуска.

beta
# Энтропия - мера хаоса в машинном обучении. beta - сила регуляризации энтропии, которая делает политику «более случайной». Это гарантирует, что агенты должным образом исследуют пространство действия во время обучения. Увеличение этого параметра обеспечит выполнение большего количества случайных действий.

epsilon
# Параметр допустимого расхождения между старой и новой политикой. Влияет на скорость изменения политики во время обучения. 

lambd 
# Параметр регуляризации (лямбда), насколько агент полагается на свою текущую оценку стоимости при расчете обновленной оценки стоимости. Низкие значения соответствуют большему полаганию на текущую оценку ценности, а высокие значения соответствуют большему полаганию на фактические вознаграждения.

num_epoch 
# Количество проходов через буфер опыта при выполнении оптимизации градиентного спуска. Чем больше размер партии, тем больше это допустимо.

learning_rate_schedule 
# Параметр, определяющий, как скорость обучения изменяется с течением времени. Для PPO в документации рекомендовано снижать скорость обучения до значения max_steps, чтобы обучение сходилось более стабильно. О

linear
# скорость обучения уменьшается линейно, достигая 0 на max_steps, сохраняя при constant этом скорость обучения постоянной для всего тренировочного прогона.

network_settings Раздел, содержащий настройки нейронной сети.

normalize 
# Параметр определяет применяется ли нормализация к входным данным векторных наблюдений. Нормализация может быть полезна в случаях со сложными задачами непрерывного управления. По умолчанию false.

hidden_units 
# Количество единиц в скрытых слоях нейронной сети.

num_layers 
# Количество скрытых слоев в нейронной сети. #Для простых задач меньше слоев, скорее всего, будут обучать быстрее и эффективнее.

reward_signals 
# Раздел позволяет задавать настройки как для внешних и внутренних сигналов вознаграждения. Каждый сигнал вознаграждения должен определять как минимум два параметра: strength и gamma, в дополнение к любым гиперпараметрам, специфичным для класса.

extrinsic 
# Dнешние сигналы вознаграждения(если они есть)

gamma 
# Фактор скидки для будущих вознаграждений, поступающих из окружающей среды. Это можно рассматривать как то, как далеко в будущем агент #должен заботиться о возможных вознаграждениях. Должен быть строго меньше 1.

strength 
# (по умолчанию = 1.0) коэффициент на который умножается вознаграждение. 

max_steps 
 # Количество шагов необходимого для завершения обучения. Если в вашей среде есть несколько агентов с одинаковым именем поведения, все шаги, предпринятые этими агентами, будут max_steps учитываться в одном и том же счетчике.

time_horizon 
# Сколько шагов опыта необходимо собрать для каждого агента, прежде чем добавить его в буфер опыта. Это позволяет усреднять результаты обучения агента, что упрощает оценку результатов.

summary_freq 
# Количество опытов, которое необходимо собрать перед созданием и отображением статистики обучения. Это определяет детализацию #графиков в Tensorboard.
```


## Задание 3
### Доработайте сцену и обучите ML-Agent таким образом, чтобы шар перемещался между двумя кубами разного цвета. Кубы должны, как и в первом задании, случайно изменять координаты на плоскости.

```C#
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Sensors;
using Unity.MLAgents.Actuators;

public class RollerAgent : Agent
{
    Rigidbody rBody;
    void Start()
    {
        rBody = GetComponent<Rigidbody>();
    }

    public GameObject Target1;
    public GameObject Target2;
    private bool target1Collected;
    private bool target2Collected;

    public override void OnEpisodeBegin()
    {
        if (this.transform.localPosition.y < 0)
        {
            this.rBody.angularVelocity = Vector3.zero;
            this.rBody.velocity = Vector3.zero;
            this.transform.localPosition = new Vector3(0, 0.5f, 0);
        }
        Target1.transform.localPosition = new Vector3(Random.value * 8 - 4, 0.5f, Random.value * 8 - 4);
        Target2.transform.localPosition = new Vector3(Random.value * 8 - 4, 0.5f, Random.value * 8 - 4);
        Target1.SetActive(true);
        Target2.SetActive(true);
        target1Collected = false;
        target2Collected = false;
    }

    public override void CollectObservations(VectorSensor sensor)
    {
        sensor.AddObservation(Target1.transform.localPosition);
        sensor.AddObservation(Target2.transform.localPosition);
        sensor.AddObservation(this.transform.localPosition);
        sensor.AddObservation(target1Collected);
        sensor.AddObservation(target2Collected);
        sensor.AddObservation(rBody.velocity.x);
        sensor.AddObservation(rBody.velocity.z);
    }

    public float forceMultiplier = 10;
    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        Vector3 controlSignal = Vector3.zero;
        controlSignal.x = actionBuffers.ContinuousActions[0];
        controlSignal.z = actionBuffers.ContinuousActions[1];
        rBody.AddForce(controlSignal * forceMultiplier);
        float distanceToTarget1 = Vector3.Distance(this.transform.localPosition, Target1.transform.localPosition);
        float distanceToTarget2 = Vector3.Distance(this.transform.localPosition, Target2.transform.localPosition);
        if (!target1Collected & distanceToTarget1 < 1.42f)
        {
            target1Collected = true;
            Target1.SetActive(false);
        }
        if (!target2Collected & distanceToTarget2 < 1.42f)
        {
            target2Collected = true;
            Target2.SetActive(false);
        }
        if (target1Collected & target2Collected)
        {
            SetReward(1.0f);
            EndEpisode();
        }
        else if (this.transform.localPosition.y < 0)
        {
            EndEpisode();
        }
    }
}

```

**Результаты обучения нового скрипта**
![Training2](https://user-images.githubusercontent.com/104727697/198285105-345b9454-408d-4169-9258-0ede6610bb87.png)


## Выводы

Узнал, как работать с ML-агентом и обучать его. Узнал, что при увеличении количества копий, нейросеть обучается быстрее. Один из вариантов использования нейросетей - это налаживание игрового балланса.

Игровой баланс - одно из важнейших понятий в играх, так как от него зависит равенство взаимодействий тех или иных объектов, правил, механик. 
Настраивать игровой баланс очень сложно, нужно учитывать много факторов, однако нейросети могут с этим очень сильно помочь. Например, нейросети могут подстраивать степень сложности окружающего мира под игрока, поэтому развивая себя игрок одновременно развивает и мир вокруг. Нейросети могут анализировать пикрейт персонажей в многопользовательской игре и уменьшать характеристики тех героев, на которых он повышен

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
