# Ruby Lab 2021-2022

## Домашние задания
### Задание 1
1. В папке с домашним заданием `hometask-1` создать файл `hello_world.rb` с кодом, который выводит в консоль "Hello world!".
2. Файл должен быть исполняемым.

### Задание 2
1. Завести аккаунт с почтовым ящиком iTechArt на [codewars](https://www.codewars.com/).
2. Решить онлайн [задание](https://www.codewars.com/kata/56747fd5cb988479af000028/train/ruby).
3. Код с решением поместить в файл `get_middle_charachter.rb` в папку с домашним заданием `hometask-2`.
4. В этот же файл добавить функцию `run_cli`, которая ожидает ввод пользователя.
Пример работы с вводом и выводом был разобран на воркшопе.
Если пользователь ввел `exit!`, программа должна завершиться.
Если пользователь ввел пустую строку, программа должна вывести сообщение об ошибке и ожидать следующий ввод пользователя.
В остальных случаях в консоль выводится результат вызова функции `get_middle` c введенной строкой,
после чего программа ожидает следующий ввод пользователя.
Файл должен быть исполняемым.
Пример работы программы:
```
$ ./get_middle_character.rb
Enter string:

String can not be blank!
Enter string:
test
Middle character: es
Enter string:
exit!
```

### Задание 3
1. Решить онлайн [задание](https://www.codewars.com/kata/56a32dd6e4f4748cc3000006/train/ruby).
2. Код с решением поместить в файл `rainfall.rb` в папку с домашним заданием `hometask-3`.
3. В этот же файл добавить функцию `run_cli`, которая ожидает ввод пользователя.
Если пользователь ввел `exit!`, программа должна завершиться.
Если пользователь ввел пустую строку, программа должна вывести сообщение об ошибке и ожидать следующий ввод пользователя.
В остальных случаях в консоль выводится результат вызова функции `mean` и функции `variance` c введенной строкой,
после чего программа ожидает следующий ввод пользователя.
Файл должен быть исполняемым.
Пример работы программы:
```
$ ./rainfall.rb
Enter city name:

City name can not be blank!
Enter city name:
London
Rainfall mean: 51.199999999999996
Rainfall variance: 57.42833333333374
Enter city name:
exit!
```

### Задание 4
#### Задание 4.1
1. Код с решением поместить в файл `my_array_rotate.rb` в папку с домашним заданием `hometask-4`.
2. Рacширить класс `Array` методaми `lab_rotate` и `lab_rotate!`, которые реализуют циклический сдвиг.  
Метод `lab_rotate` циклически сдвигает массив без изменения объекта.  
Метод `lab_rotate!` циклически сдвигает массив c изменением объекта.  
В качестве аргумента метод принимает число элементов, на которое нужно сдвинуть массив.  
Если число положительное, то массив циклически сдвигается влево.  
Если число отрицательное, то массив циклически сдвигается вправо.  
По умолчанию массив циклически сдвигается на 1 элемент влево.  
Задание подразумевает самостоятельную реализацию циклического сдвига, т.е. использовать [Array#rotate](https://ruby-doc.org/core-3.0.2/Array.html#method-i-rotate) или [Array#rotate!](https://ruby-doc.org/core-3.0.2/Array.html#method-i-rotate-21) нельзя.  
C ростом размера сдвига скорость циклического сдвига, реализованного в `Array#lab_rotate` и `Array#lab_rotate!`, не должна значительно отличаться от скорости сдвига, реализованного в `Array#rotate` или `Array#rotate!` соответственно.  
С помощью модуля [Benchmark](https://ruby-doc.org/stdlib-2.5.3/libdoc/benchmark/rdoc/Benchmark.html) произвести сравнение производительности `Array#lab_rotate` и `Array#lab_rotate!` c `Array#rotate` и `Array#rotate!` соответственно.  
Сравнение описать в файле `my_array_rotate_benchmark.rb`.

Пример работы программы:
```
$ irb
irb(main):001:0> require './my_array_rotate.rb'
=> true
irb(main):002:0> arr = (1..7).to_a
=> [1, 2, 3, 4, 5, 6, 7]
irb(main):003:0> arr.lab_rotate
=> [2, 3, 4, 5, 6, 7, 1]
irb(main):004:0> arr
=> [1, 2, 3, 4, 5, 6, 7]
irb(main):005:0> arr.lab_rotate!(-3)
=> [5, 6, 7, 1, 2, 3, 4]
irb(main):006:0> arr
=> [5, 6, 7, 1, 2, 3, 4]
```

#### Задание 4.2
1. Код с решением поместить в файл `my_hash.rb` в папку с домашним заданием `hometask-4`.
2. Реализовать класс `MyHash` подобно классу [Hash](https://ruby-doc.org/core-3.0.2/Hash.html).  
Для класса `MyHash` необходимо реализовать следующие операции: 
* Запись по ключу
* Чтение по ключу
* Удаление пары ключ-значение
* Подсчет размера хэша
* Очищение всех пар ключ-значение без создание нового объекта.  
Класс должен быть расширен модулем [Enumerable](https://ruby-doc.org/core-3.0.2/Enumerable.html).  
Задание подразумевает самостоятельную реализацию хэша, т.е. использовать [Hash](https://ruby-doc.org/core-3.0.2/Hash.html) нельзя.  
C ростом числа пар ключ-значение скорост записи и чтения по ключу не должна значительно отличаться от стандартной имплементации [Hash](https://ruby-doc.org/core-3.0.2/Hash.html).  
С помощью модуля [Benchmark](https://ruby-doc.org/stdlib-2.5.3/libdoc/benchmark/rdoc/Benchmark.html) произвести сравнение производительности реализаванных операций `MyHash` с операциями в `Hash`.  
Сравнение описать в файле `my_hash_benchmark.rb`.

Пример работы программы:
```
$ irb
irb(main):001:0> require './my_hash.rb'
=> true
irb(main):002:0> my_hash = MyHash.new
=> #<MyHash:0x00007ff1d38a3d98 ... >
irb(main):003:0> my_hash['hello'] = 'world'
=> "world"
irb(main):004:0> my_hash['hello']
=> "world"
irb(main):005:0> my_hash['foo']
=> nil
irb(main):006:0> my_hash.each do |k, v|
irb(main):007:1* print "#{k} => "
irb(main):008:1> puts v
irb(main):009:1> end
hello => world
=> #<MyHash:0x00007ff1d38a3d98 ... >
```

## Гайд по оформлению домашнего задания
### Краткое описание
Код каждого домашнего задания должен быть отправлены на проверку в качестве PR (Pull Request).
Только после того, как PR был проверен и одобрен ментором, PR можно мержить.
Задание считается выполненым только после того, как оно было замержено.
Все домашние задания должны находиться в папке с вашим ником в GitHub.

### Инструкция по оформлению
1. [Сделать форк](https://docs.github.com/en/get-started/quickstart/fork-a-repo#forking-a-repository) этого репозитория
2. [Сделать клон](https://docs.github.com/en/get-started/quickstart/fork-a-repo#cloning-your-forked-repository) своего форка
3. [Создать ветку](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository#creating-a-branch) со своим ником и названием домашнего задания
4. В корне репозитория создать папку с именем своего никнейма в GitHub
5. В своей папке создать папку с названием домашнего задания
6. В папке с домашним заданием создать все необходимые файлы с кодом
7. По завершению задания [добавить изменения](https://github.com/git-guides/git-add), [cоздать](https://github.com/git-guides/git-commit)  [запушить](https://github.com/git-guides/git-push) коммит в свою ветку
8. [Создать PR](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) с домашним заданием для ветки rubylab-2021-2022
9. Скинуть ссылку на PR своему ментору и дождаться его ревью
10. [Замержить](https://docs.github.com/en/github/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request) PR, если ментор одобрил PR
