# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Лапп Георгий Валентинович
- РИ210943
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
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Вывести "Hello World!" на unity и на python.
```py
print("Hello World!")
```
- код для python
- ![image](https://user-images.githubusercontent.com/32997569/192461241-bacd7675-2b93-4aef-9aae-f814b37eb86c.png)

```cs
public class HelloWorld : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        print("Hello World!");
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}

```

-код для unity

![image](https://user-images.githubusercontent.com/32997569/192461340-39a907b9-2956-4ba4-a8e0-d64b5c4224a4.png)



## Задание 2
### Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.

Величина loss не должна стремиться к нулю. Величина loss показывает потери для каждого набора данных и при оптимальных настройках коэффициента градиента спуска и количества итераций покажет наименьшие потери. Величина loss может стремиться к нулю если точки из набора данных будут лежать на одном радиус-векторе и настройки коэффициента градиента спуска и количества итераций будут оптимальны. Но для каждного набора данных предел loss свой.
Все эти выводы можно сделать из функции loss_function из которой мы и получаем величину loss.

```py
# Изначальный набор точек при котором предел loss около, 180
x = [3,21,22,34,54,34,55,67,89,99]
x = np.array(x)
y = [2,22,24,65,79,82,55,130,150,199]
y = np.array(y)
# для следующего набора данных loss будет стремиться к нулю (учитывая что остальные данные оптимальны)
x = [3,22,24,34,54,82,55,130,150,199]
x = np.array(x)
y = [3,22,24,34,54,82,55,130,150,199]
y = np.array(y)
def loss_function(a,b,x,y):
  num=len(x)
  prediction = model(a,b,x)
  return(0.5/num)*(np.square(prediction-y)).sum()
```
![image](https://user-images.githubusercontent.com/32997569/192457176-fe48beb0-7cec-4fd3-9337-0058a32b2f26.png)
полный код доступен  [в репозитории](https://github.com/GeorgeLapp/DA-in-GameDev-lab1/blob/main/Script.py).
## Задание 3
### Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.
Lr- коэффициент градиета спуска, этот вывод можно сделать из следующего участка кода:
```py
def optimize(a,b,x,y):
  num=len(x)
  prediction = model(a,b,x)
  da=(1.0/num)*((prediction -y)*x).sum()
  db=(1.0/num)*((prediction -y).sum())
  a=a-Lr*da
  b = b-Lr*db
  return a,b

```
 Lr - изменение велечин стремящееся к нулю, линейная часть приращения функции или дифференциал. 
 Если мы будем учеличивать Lr то заметим, что фунция быстрее возрастает по оси oy:
 при Lr 0,000001  и 5 итерациях:
 
 ![image](https://user-images.githubusercontent.com/32997569/192460444-f82a5e09-0623-47c7-8584-3607f06e008a.png)
 
 при Lr 0,0001  и 5 итерациях:
 
![image](https://user-images.githubusercontent.com/32997569/192461745-61995cb1-5aa4-47ec-961c-7c900578ae6c.png)


## Выводы

П

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
