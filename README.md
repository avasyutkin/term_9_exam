## Экзамен "Разработка и эксплуатация защищенных автоматизированных систем"

### Модульное тестирование 

Для проведения модульного тестирования функции, определяющей квадратичные вычеты по модулю, разработанного в рамках курса «Программирование криптографических алгоритмов», был использован предустановленный в PyCharm фреймворк `unittest`. 

#### Порядок работы: 
1. Создаем файл `main_test.py`

2. Делаем импорт фреймворка для модульного тестирования и файла `main` с реализацией тестируемой функции:
   ``` 
   import unittest
   import main
   ```

3. Создаем класс `VasyutkinTestCase` и в нем определяем функции для тестирования, например `def test_positive(self)`

4. Вызваем функцию, выполняющую сравнение значения, которое вернула тестируемая функция в результате запуска, с заранее подсчитанным верным значением `self.assertEqual(result, data_output)`

5. Запускаем тест из интерфейса IDE кнопкой `Run`

#### Результат

После зауска теста в консоли видим следующий результат:

<img width="1440" alt="Снимок экрана 2023-01-26 в 10 55 18" src="https://user-images.githubusercontent.com/43503189/214784373-de621302-4882-4578-8720-ce9a44ca0537.png">

Как можем видеть на скрине одна из функций прошла тест не успешно: фактический результат не соответствует ожидаемому.

---

### Статический анализ

Для проведения статического анализа модуля, выполняющего анализ эллиптических кривых, разработанного в процессе изучения курсе «Программирование криптографических алгоритмов», был использован инструмент `flake8`.

#### Порядок работы: 
1. Устанавливаем через терминал статический анализатор: 
   ``` 
   pip install flake8
   ```
  
2. Запускаем модуль: 
   ``` 
   flake8 main.py
   ```

Статически анализатор нашел следующие ошибки (21) и описал их в консоли:
* 9 ошибок типа `N802`, `N803` и `N806` связаны с тем, что в названии переменных и функций используются заглавные буквы
* 5 ошибок типа `E501` связаны с тем, что длина строки превышает рекомендуемую 
* ошибка типа `E265` заключается в том, что комментарий должен начинаться с '# ', а не '#'
* ошибка типа `E303` заключается в том, что перед функцией стоит три пустых строчки вместо рекомендуемых двух
* 2 ошибки типа `E741` связаны с тем, что переменные имеют не осмысленные названия
* ошибка типа `W292` связана с тем, что файл не оканчивается пустой строкой
* ошибка типа `E225` связана с тем, что между оператором и названием переменной отсетствует пробел

<img width="1440" alt="Снимок экрана 2023-01-26 в 11 23 03" src="https://user-images.githubusercontent.com/43503189/214788933-8896e6d3-f721-495a-a031-f2457a571d5d.png">

#### Исправление ошибок
Исправим ошибку `E265` и одну `E501`:
<img width="1264" alt="Снимок экрана 2023-01-26 в 12 10 37" src="https://user-images.githubusercontent.com/43503189/214798182-dcf3ad83-aeb4-4f0b-8630-30f05cca9b86.png">
<img width="1264" alt="Снимок экрана 2023-01-26 в 12 10 57" src="https://user-images.githubusercontent.com/43503189/214798247-344e89bf-e085-4d43-8ea1-91d00bd80dfe.png">

Исправим ошибку `E303`:
<img width="1266" alt="Снимок экрана 2023-01-26 в 12 13 12" src="https://user-images.githubusercontent.com/43503189/214798648-fc77c691-503a-488a-8391-d2010316415b.png">
<img width="1266" alt="Снимок экрана 2023-01-26 в 12 13 27" src="https://user-images.githubusercontent.com/43503189/214798682-af14a54a-9ec7-4930-add5-d9787072f5d0.png">

