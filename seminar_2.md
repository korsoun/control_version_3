# Инструкция по работе с языком разметки Markdown и системой контроля версий

## Возможности Markdown

Markdown  - это один из языков разметки, поэтому естественно, что он позволяет задавать параметры форматирования текста: отображение текста, указания на заголовки и списки, на интерактивные элементы и др. В этой инструкции основные возможности данного языка разметки.

### Заголовки

Для установки заголовков используются символы #, количество которых зависит от уровня соответствующего заголовка. Markdown допускает 6 уровней вложенности, то есть допускается ставить заголовки от # до ######.

### Форматирование текста

Основные параметры форматирования текста - это отображение текста в полужирном, курсивном, подчеркнутом виде и другие варианты.

* Для *курсивного* начертания необходимо заключить текст в звездочки ( \*текст\*)

* Для **полужирного** начертания необходимо заключить текст в двойные звездочки (\*\*текст\*\*)

* Для ***полужирного курсивного*** начертания текст заключается в тройные звездочки (\*\*\*текст\*\*\*)

* Для ~~зачеркнутого~~ текста его необходимо заключить в двойные тильды (\~\~текст\~\~)

Это не единственный вариант задать тип оформления текста. При работе с Markdown  для задания полужирных и курсивных наертаний можно использовать символ _ и даже комбинировать его со звездочкой. Это удобно при работе с текстом, где необходимо ставить подобные символы, для избежания путаницы.


### Создание списков

Markdown позволяет создавать нумерованный и ненумерованный списки

Для создания нумерованного списка необходимо указывать перед элементом списка его порядковый номер по схеме (1. Элемент). 

1. Первый элемент
2. Второй элемент

При этом не обязательно делать двойной отступ для задания перехода на новую строку. Достаточно прописать цифру, точку, после пробела элемент списка, и текст автоматически будет распознан как список. Работать со списком можно как в обычном текстовом редакторе.

Для создания ненумерованного списка необходимо перед элементом поставить звездочку или дефис (* Элемент или - Элемент). Эти варианты не совсем равноправны - список будет составлен даже при совместном использовании обоих символов, но при использовании разных символом отступ между соответствующими элементами будет больше. В примере первые два элемента вставлены в список звездочкой, а третий и четвертый - дефисом.

* Первый элемент
* Второй элемент
- Третий элемент
- Четвертый элемент

### Вставка объектов

 #### Вставка цитат

Для того, чтобы вставить цитату, используется конструкция: \> цитируемый текст. При этом ставить такой символ необходимо перед каждой строкой в цитировании, иначе части цитаты не будут находиться в едином блоке, либо что-то из этого блока выпадет совсем.

Пример: 
> В общем, у нас большой опыт отсутствия опыта
>
> Терри Пратчетт

#### Вставка таблиц

Markdown позволяет создавать простые таблицы с помощью комбинаций символов | и -. Создадим простую таблицу из шести ячеек:

Загол1|Загол2|Загол3

------|------|------

Текст1|Текст2|Текст3

Получается такая таблица:

Загол1|Загол2|Загол3
------|------|------
Текст1|Текст2|Текст3


#### Вставка линий

Для вставки линий необходимо три или более раз ввести символ _ или -.

Получающаяся линия:
___


#### Вставка ссылок

Для того, чтобы вставить ссылку, необходимо воспользоваться следующей конструкцией: [описание ссылки](адрес ссылки).

Выглядит ссылка так:
[уютный журнал о естественнонаучном](https://batrachospermum.ru)

#### Вставка изображений

Конструкция для вставки изображений почти такая же: ![подпись](ссылка на изображение).

Картинка для примера:

![котик](https://storage.theoryandpractice.ru/tnp/uploads/image_unit/000/156/586/image/base_87716f252d.jpg)

Текст в квадратных скобках важен: он отображается в том случае, если загрузка изображения не удалась, он будет прочитан скринридерами, а еще именно по нему происходит поиск изображения в поисковиках.




## Работа с GIT

### Что такое GIT

 GIT - это самая популярная система контроля версий (система, предназначенная для контроля вносимых изменений в код, отслеживания и управления ими). Она используется для огромного количества проектов, может работать под управлением различных операционных систем. 

### Основные команды

 Прежде всего, но это совершенно естественно, необходимо установить GIT на свой ПК. Перед этим устанавливаем среду для разработки, мы будем использовать терминал в этой среде для отправки команд в GIT. После установки в терминал отправляются две команды: "git config --global user.name имя_пользователя" и "git config --global user.email адрес_электронной_почты". Таким образом происходит "представление" пользователя системе. Стоит отметить, что подойти к этому шагу стоит ответственно, так как эти сведения отображаются в коммитах, которые мы будем делать. Если в ответ на отправляемые команды система не дает какие-либо ответы, а просто начинает ждать следующую команду, то "представление" завершено. Проверить готовность системы к работе можно проверить и командой "git --version". В ответ на нее система выведет версию используемого ПО.

Запомним:

***git config --global user.name имя_пользователя*** - передача системе имени пользователя

***git config --global user.email адрес_электронной_почты*** - передача системе адреса эл. почты пользователя

***git --version*** - получение информации о версии продукта

 Следующим шагом в работе с GIT является создание репозитория. Репозиторий - это хранилище для файлов, создаваемых и редактируемых в процессе работы. Если совсем просто, то репозиторий - это папка, где хранятся файлы проекта. И нутри этой папки GIT осуществляет свой контроль. Для создания репозитория GIT необходимо через среду разработки открыть нужную папку и ввести команду "git init". Репозиторий создан. В дальнейшем может потребоваться переместиться в другие папки, например, для работы с другими проектами. Сделать это можно через команду "cd имя_папки", после чего снова потребуется сделать инициализацию. Команда "cd .." позволит переместиться в папках на один уровень выше текущей.

Запомним:

***git init*** - инициализация папки в качестве репозитория

***cd имя_папки*** - переход в другую папку

***cd ..*** - переход в папку уровнем выше

 Наконец, можно начать работу с проектом. В среде разработчика можно вносить изменения в проект. Но для правильной работы GIT их необходимо сохранять. И Ctlr-S не сделает всей магии. Для этого после стандартного сохранения изменений в проекте необходимо ввести две команды: "git add имя_файла" и "git commit -m 'сообщение к коммиту'". Первая команда указывает, в каком файле нужно сделать фиксацию изменений, вторая - позволяет их зафиксировать и сделать комментарий к ним. В дальнейшем возможно просматривать предыдущие версии проекта и сделанные изменения через команду "git log". В терминале появится список сделанных к данному файлу коммитов с их идентификаторами, временем и автором изменений, расположенных снизу вверх. Для выхода из режима просмотра логов в терминале нужно нажать клавишу Q. Для более подробного просмотра интересующей версии можно воспользоваться командой "git checkout идентификатор_коммита", в котором можно ввести не весь идентификатор, а 4 первых символа. Для проверки проекта на предмет не внесенных в GIT изменений служит команда "git status", котрая выведет название файла, в котором есть не внесенные изменения. Для просмотра изменений, которые сделаны за текущий сеанс работы и еще не внесены в систему можно воспользоваться командой "git diff". В терминале появятся изменения, по которым еще не внесены коммиты. Выйти из этого режима также можно по клаише Q.

Запомним:

***git add имя_файла*** - указание на файл, изменения в котором нужно добавить к рассмотрению

***git commit -m 'текст комментария'*** - фиксация изменений и создание комментария к ним

***git log*** - просмотр списка сделанных коммитов

***git checkout идентификатор_коммита*** - переход к конкретному коммиту

***git status*** - проверка на наличие не отслеживаемых изменений

***git diff*** - вывод изменений, которые еще не сохранены



**clear** - очищение терминала





### Ветвление

  Линейная работа с проектом, когда в него вносятся изменения, сохраняются, согласовываются, а затем идет работа с новыми изменениями, не всегда применима. В больших проектах может быть задействована целая команда исполнителей, каждому члену которой поручена своя задача, и ждать выполнения предыдущих этапов для начала нового оказывается очень долго и затратно. В этом случае работу с проектом желательно вести  разветвленную, но и контролировать ее ход сложнее. Собственно, для этого и придуманы системы контроля версий. Система GIT предусматривает возможность работы с ветками проекта, где ветка - это работа с параллельной версией проекта. При этом члены команды получают возможность выполнять свою часть работы одновременно, объединяя версии проекта, над которыми они работали, по достижении необходимого результата. 

  Работа с проектом всегда начинается в стартовой ветке, по умолчанию названной master. Для создания новой ветки применяется команда "git branch имя_ветки". Если ввести эту команду, не прописывая название конкретной ветки, то система выдаст список всех имеющихся на данный момент веток, указав, в какой именно ветке сейчас находится пользователь. Для перехода между ветками применяется уже известная команда "git checkout имя-ветки"

Запомним:

**git branch** - вывести список всех имеющихся сейчас веток

**git branch имя_ветки** - создать новую ветку с заданным именем

**git checkout имя_ветки** - перейти  указанную ветку

**git checkout -b имя_ветки** - создать новую ветку и сразу в нее перейти

  Когда работа в какой-либо ветке закончена и одобрена, информацию из нее необходимо добавить к главной ветке. Сделать это можно командой "git merge имя_ветки". Важно. Эта команда прописывается, когда пользователь перешел в ту ветку, куда необходимо влить изменения. Прописывается же в команде имя ветки, которую необходимо слить с главной. Кстати, с помощью команды "git log --graph" можно посмотреть список коммитов с графическим представлением имеющихся веток для большей наглядности. После слияния веток необходимость в побочной ветке зачастую отпадает, так что ее можно удалять. Сделать это можно по команде "git branch -d имя_ветки". Удалить можно и с использованием флага -D, но такой флаг удалит ветку в любом случае, даже если в ней остались не сохраненные или не влитые изменения.

Запомним:

***git merge имя_ветки*** - слить названную ветку с текущей

***git branch -d имя_ветки*** - удалить названную ветку

***git log --graph*** - представить коммиты с графическим представлением веток

  При работе в разных ветках может случиться такое, что в одном и том же месте проекта велась работа в разных ветках. Тогда в каждой ветке к данному месту будут свои изменения. Попытка слить данные ветки приводит к конфликту: система не может атоматически слить ветки с учетом изменений. Для разрешения конфликта пользователю предлагаются 4 варианта:
    
    1. Принять только первый вариант (исходный) - принимается вариант, созданный в принимающей ветке
    2. Принять только второй вариант (предлагаемый) - принимается вариант, созданный в сливаемой ветке
    3. Принять оба варианта - система оставит вариант принимающей ветки, ниже будет добавлен вариант из сливаемой ветки
    4. Сравнить варианты - вообще говоря, это не выход из конфликта, но система покажет различия двух конфликтующих версий, исходя из чего можно сделать выбор нужного действия  

### Удаленные репозитории

Указанные выше команды позволяют проделывать большой объем работы с репозиториями. Но эти репозитории хранятся на ПК пользователя, поэтому работать с ними может только этот пользователь. Если возникает необходимость делиться результатами своей работы или вести совместную работу над проектом, то возникает ряд неудобств. Например, при необходимости передать репозиторий другому пользователю приходится использовать флеш-накопители, передавать или пересылать их, передавать архивы по электронной почте. Кроме того осложняется работа непосредственно по отслеживанию изменений и по их одобрению. Для этого были придуманы сервисы для организации работы удаленных репозиториев, которые позволяют копировать сравнительно быстро нужный репозиторий на свой ПК, передавать его со своего ПК или даже работать со своим репозиторием и делиться им напрямую в системе. Самым известным и популярным сервисом является **GITHub**.

Для работы с сервисом необходима авторизация. После этого пользователю открываются все ее возможности. GITHub позволяет создавать собственные репозитории, редактировать их в сервисе, вставлять различные элементы, просматривать проекты других пользователей, копировать их, проводить изменения и предлагать эти изменения их авторам.

Для работы в сервисе основные понятия - это Fork и Pull request. Кнопка Fork позволяет скопировать чей-либо репозиторий себе внутри сервиса, кнопка Pull request позволяет предложить сделанные изменения автору скопированного репозитория.

Для того, чтобы сохранить репозиторий из сервиса на свой ПК можно воспользоваться обычным скачиванием архива, но для системы GIT есть команда "git clone адрес_репозитория", где адрес репозитория - это ссылка на него в сервисе GITHub.

Команда "git pull" позволяет скачать внешний репозиторий и слить его с текущей версией локального.

Команда "git push" наоборот позволяет отправить внешний репозиторий на сервис, но для этого необходимо быть авторизованным для возможности управления удаленным репозиторием.

Запомним:

***git clone адрес_репозитория*** - скопировать удаленный репозиторий на свой ПК

***git pull*** - скачать удаленный репозиторий и слить его с версией на ПК

***git push*** - отправить версию репозитория с ПК на удаленный репозиторий

***Fork*** - копировать удаленный репозиторий себе в сервисе GITHub

***Pull request*** - предложить сделанные изменения в репозитории его автору

Для того, чтобы правильно сделать Pull request, необходимо придерживаться следующего порядка действий:

1. Сделать Fork выбранного репозитория
2. Сделать Clone скопированной версии репозитория на свой ПК
3. Создать новую ветку и внести в нее предлагаемые изменения
4. Сделать необходимые коммиты
5. Отправить свою версию на свой репозиторий в GITHub
6. Предложить изменения автору через Pull request

Чтобы отправить изменения в репозиторий на GITHub, необходимо следующее:

1. Получить ссылку на репозиторий, который нужно изменить
2. Команда git remote add origin ссылка_на_репозиторий
3. git branch -M main (согласование главных веток репозиториев)
4. git push -u origin main

Обратите внимание, данные команды в общем виде выглядят как

***git remote add короткое_имя ссылка_на_репозиторий***

***git push короткое_имя имя_отправляемой_ветки***

Но из-за значительного объема работ по согласованию репозиториев, проводящегося автоматически при клонировании репозитория, короткое имя автоматически присваивается только что клонированному репозиторию 'origin', а ветке - 'main'. Поэтому представленные ранее команды и выглядят так. Помните про общий вид этих команд, если при работе с удаленным репозиторием что-то не будет получаться.
