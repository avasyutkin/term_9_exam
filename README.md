## Экзамен "Разработка и эксплуатация защищенных автоматизированных систем"

### Модульное тестирование 

Для проведения модульного тестирования функции, определяющей квадратичные вычеты по модулю, был использован предустановленный в PyCharm фреймворк `unittest`. 

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

После зауска теста, в консоли видим следующий результат:

<img width="1440" alt="Снимок экрана 2023-01-26 в 10 55 18" src="https://user-images.githubusercontent.com/43503189/214784373-de621302-4882-4578-8720-ce9a44ca0537.png">

Как можем видеть на скрине, одна из функций прошла тест не успешно: фактический результат не соответствует ожидаемому.

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

Статически анализатор нашел следующие ошибки и описал их в консоли:

<img width="1440" alt="Снимок экрана 2023-01-26 в 11 23 03" src="https://user-images.githubusercontent.com/43503189/214788933-8896e6d3-f721-495a-a031-f2457a571d5d.png">

