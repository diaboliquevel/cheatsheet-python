# notes-python
## Самые главные команды в командной строке Windows и Linux

|  Значение      | Windows        | Linux / MacOS |
| ------------- |-------------:| -----:|
| Переход в другую директорию     | cd | cd |
| Создание файла    | copy con     | touch|
| Создание папки | mkdir  |  mkdir |
| Удаление файла | del, erase | rm; rm -rf -- удалить папку и все файлы в ней |
| Удаление папки    | rmdir      |   rmdir |
| Вывод на экран сообщения | echo   |  echo |
| Вывод на экран содержимого файла | type  | cat|
| Копирование файлов     | copy, xcopy | cp |
| Переименование файлов   | ren, rename      |  mv |
| Перемещение файлов   | move  |  mv |
| Поиск файлов | where     |   find, locate |
| Вывод списка файлов и каталогов| dir |  ls, dir |
| Помощь |   help  |  apropos, man, whatis  |


**Циркумфлекс** (вот этот знак "^") означает нажатие клавиши с Ctrl (^C = Ctrl + C).

^C — Прерывает команду, ну это все знают.

^S — Приостанавливает выполнение команды, а потом запускает.

^I — Аналог Tab, перебирает папки и файлы.

^M — Аналог Enter.

^H — Аналог Backspace.

## Работа с Python

|Команда| Значение|
|-------| -------:|
|python| Запустить питон в терминале |
|python --version| Посмотреть версию питона|
|pip freeze| Посмотреть список установленных пакетов|
|pip install| Установить пакет|
|pip uninstall| Удалить пакет|
|pip show| Показать информацию о конкретном пакете|
|pip search| Найти пакет (если вы хотите установить что-то новое, но точно не помните название)|

Подробнее про работу с pip можно почитать [на официальном сайте с документацией](https://pip.pypa.io/en/stable/).
## Работа с Git

Как устроена команда?
* сначала вызов программы: например, git
* затем команда для этой программы: например, commit 
* затем опции этой команды, если они есть: -m
* затем значение опции: "Сообщение коммита"

Вместе получается `git commit -m "Сообщение коммита"`. Обратите внимание, что между всеми частями команды ставятся проблелы! 

У git очень много возможностей, и про работу с ним написаны толстые книжки (см. пример ниже :D). Здесь перечислены только самые часто употребляемые команды.

|Команда| Значение|
|-------| -------:|
|git clone| Склонировать репозиторий по указанной ссылке|
|git pull| Скачать изменения из удаленного репозитория|
|git init| Создать репозиторий |
|git status| Посмотреть статус изменений|
|git add| Добавить указанные файлы в список отслеживаемых|
|git add \*| Добавить все файлы|
|git rm| Удалить файлы|
|git commit -m| Закоммитить изменения; после -m в кавычках пишется сообщение о том, что изменено|
|git push| Отправить изменения в удаленный репозиторий|
|git log| Посмотреть журнал действий|

Более продвинутые вещи -- например, как исправлять ошибки или как работать с разными ветками -- можно почитать в [пошаговом тьюториале](https://git-scm.com/book/en/v1/Git-Basics-Undoing-Things) на официальном сайте.

**NB!** Чтобы не печатать длинные пути целиком, существует *автозаполнение*: набираете 1-2 первые буквы, нажимаете tab и вуаля!

### Как настроить авторизацию в Git?

После установки git необходимо его настроить, это делается с помощью двух команд:

`git config --global user.name "ваш логин на github"`

`git config --global user.email "почту, которую указали при регистрации на GitHub.com"`



{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Простые вычисления в Python"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "3"
      ]
     },
     "execution_count": 2,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Если строчка начинается с решетки -- это комментарий.\n",
    "# Комментарий объясняет, что происходит в том или ином месте кода.\n",
    "# Комментарии -- это очень хорошо. Не забывайте писать комментарии!\n",
    "\n",
    "# Создаем переменные х и y и присваиваем им значения 1 и 2 соответственно\n",
    "x = 1\n",
    "y = 2\n",
    "\n",
    "# Считаем сумму \n",
    "x + y"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Вычисления произведены, но ответ 3 не остался в памяти. Если мы хотим его сохранить, нужно записать его в какую-нибудь переменную."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "3\n"
     ]
    }
   ],
   "source": [
    "z = x + y\n",
    "print(z)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Допустим, мы хотим обновить значение переменной, добавив или отняв какое-то число. Или умножив / разделив ее на какое-то число. Это можно записать двумя способами."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {},
   "outputs": [],
   "source": [
    "# длинный\n",
    "z = z + 5\n",
    "\n",
    "# короткий\n",
    "z += 5"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Иксы и игреки -- это скучно, так что давайте лучше посчитаем котиков и пёсиков (а заодно запоминим, что переменные нужно называть понятно!)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "15\n",
      "12\n",
      "5.0\n",
      "35\n"
     ]
    }
   ],
   "source": [
    "cats = 7\n",
    "dogs = 5\n",
    "elephants = 3\n",
    "\n",
    "animals = cats + dogs + elephants\n",
    "print(animals)\n",
    "\n",
    "domestic_animals = animals - elephants\n",
    "print(domestic_animals)\n",
    "\n",
    "# Делим животных между 3 зоопарками\n",
    "zoo_share = animals / 3\n",
    "print(zoo_share)\n",
    "\n",
    "# Помножим котиков на пёсиков, что бы это ни значило :)\n",
    "genetic_experiment = cats * dogs\n",
    "print(genetic_experiment)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Типы данных\n",
    "\n",
    "А если мы хотим распечатать не только числа, но и какое-то текстовое пояснение?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Всего животных: 15\n",
      "Всего животных: 15\n",
      "Всего животных: 15\n"
     ]
    }
   ],
   "source": [
    "# Можно сделать так\n",
    "print(\"Всего животных: \" + str(animals))\n",
    "\n",
    "# А можно так\n",
    "print(\"Всего животных: %s\" % (animals))\n",
    "\n",
    "# А можно вот так\n",
    "print('Всего животных: {}'.format(animals))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Если же мы попробуем написать вот такое выражение, то ничего не получится."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [
    {
     "ename": "TypeError",
     "evalue": "must be str, not int",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mTypeError\u001b[0m                                 Traceback (most recent call last)",
      "\u001b[0;32m<ipython-input-6-93a03a0648be>\u001b[0m in \u001b[0;36m<module>\u001b[0;34m()\u001b[0m\n\u001b[0;32m----> 1\u001b[0;31m \u001b[0mprint\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m\"Всего животных: \"\u001b[0m \u001b[1;33m+\u001b[0m \u001b[0manimals\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m",
      "\u001b[0;31mTypeError\u001b[0m: must be str, not int"
     ]
    }
   ],
   "source": [
    "print(\"Всего животных: \" + animals)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Почему? О чем говорит эта ошибка?\n",
    "* о том, что существуют разные типы данных\n",
    "* о том, что нельзя проводить одну операцию (сложение и т.д. и т.п.) над данными разных типов\n",
    "\n",
    "Вот основные типы данных, с которыми мы будем сталкиваться.\n",
    "\n",
    "|англ|рус|название в питоне|пример|\n",
    "|----|---|-----------------|------|\n",
    "|string|строка|str|\"привет\", \"10\", \"True\"|\n",
    "|integer|целое число|int|23, 9807|\n",
    "|float|дробь (с плавающей запятой)|float|0.5, 67.0|\n",
    "|boolean|логический тип|bool|True, False|\n",
    "\n",
    "Данные можно преобразовывать из одного типа в другой:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'bool'>\n",
      "<class 'str'>\n"
     ]
    }
   ],
   "source": [
    "x = True\n",
    "print(type(x))\n",
    "\n",
    "y = str(x)\n",
    "print(type(y))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "25\n",
      "<class 'int'>\n",
      "25.0\n",
      "<class 'float'>\n"
     ]
    }
   ],
   "source": [
    "x = 25\n",
    "print(x)\n",
    "print(type(x))\n",
    "\n",
    "y = float(x)\n",
    "print(y)\n",
    "print(type(y))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Можно складывать и вычитать не только целые числа и дроби, но и строки! Это называется *конкатенация*."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "aaaaaaaaaa!\n"
     ]
    }
   ],
   "source": [
    "sound = \"a\"\n",
    "scream = sound * 10 + \"!\"\n",
    "print(scream)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "А еще можно проверять выражения на истинность и ложность. Это очень важная функция, которая не раз пригодится нам в будущем."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "True"
      ]
     },
     "execution_count": 13,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "1 > -1"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "True"
      ]
     },
     "execution_count": 14,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "6 >= 0"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "False"
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# обратите внимание, что при сравнении используется не =, а ==\n",
    "\"cat\" == \"dog\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "False"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# а теперь \"не равно\"\n",
    "2 * 2 != 4"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Variables vs Constants\n",
    "\n",
    "**Константа** -- это то, значение чего не меняется. Числа и строки -- это константы."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "1\n",
      "Hello world!\n"
     ]
    }
   ],
   "source": [
    "print(1)\n",
    "print('Hello world!')"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**Переменная** -- это контейнер, в который записывается то или иное значение. Это значение может изменяться. Если нужно сохранить информацию, то нужно записать ее в какую-либо переменную. Имя переменной -- это некий ярлык, по которому можно вызвать ее содержимое."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "30\n"
     ]
    }
   ],
   "source": [
    "x = 15 \n",
    "y = x*2\n",
    "print(y)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "This is a string\n"
     ]
    }
   ],
   "source": [
    "# теперь изменим значение y\n",
    "\n",
    "y = \"This is a string\"\n",
    "print(y)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Есть несколько служебных слов, которыми нельзя называть переменные, иначе питон не будет понимать, что с ними делать, потому что каждое из этих слов означает для него определенное действие. \n",
    "\n",
    "|  &nbsp;   | &nbsp; |   &nbsp;   |&nbsp;    | &nbsp;      |\n",
    "|-----|--|------|----|-------|\n",
    "|False|if|assert|from|finally|\n",
    "|True|elif|break|import|global|\n",
    "|None|else|continue|def|nonlocal|\n",
    "|and|while|pass|return||\n",
    "|or|for|try|yield||\n",
    "|not|in|except|class||\n",
    "|with|as|raise|lambda||\n",
    "\n",
    "Кроме того, нехорошо называть переменные и особенно функции именами стандартных питоновских функций, например:\n",
    "\n",
    "|  &nbsp;  |  &nbsp; |  &nbsp;   |\n",
    "|----|---|-----|\n",
    "|dict|int|print|\n",
    "|list|str|len|\n",
    "|set|float|sum|\n",
    "|tuple|bool|type|"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Built-in Functions\n",
    "\n",
    "А что это за стандарные функции? Это функции, которые есть в базовой сборке питона и не требуют импорта дополнительных модулей (о модулях речь пойдет в одном из следующих семинаров), например:\n",
    "\n",
    "* len() -- узнать длину выражения в скобках\n",
    "* sum() -- посчитать сумму выражения в скобках\n",
    "* print() -- распечатать значение выражения в скобках\n",
    "* count() -- посчитать количество элементов в выражении в скобках\n",
    "* type() -- узнать тип выражения в скобках\n",
    "* input() -- подхватить введенную пользователем в консоли строку\n",
    "* dict() -- превратить выражение в скобках в **словарь**\n",
    "* set() -- превратить выражение в скобках в **множество**\n",
    "* list() -- превратить выражение в скобках в **список** (он же **массив**)\n",
    "* tuple() -- превратить выражение в скобках в **кортеж**\n",
    "\n",
    "О функциях int(), str(), float() и bool() мы говорили на прошлом занятии, а о функциях dict(), set(), list() и tuple() поговорим чуть ниже.  \n",
    "\n",
    "Полный список встроенных функций можно посмотреть [вот тут](https://docs.python.org/3.3/library/functions.html)."
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.6.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
