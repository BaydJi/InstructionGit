# Инструкция по работе с Git

![Логотип Гит](111.jpeg)

**Git** - это консольная утилита, для отслеживания и ведения истории изменения файлов, в вашем проекте. Чаще всего его используют для кода, но можно и для других файлов. Например, для картинок - полезно для дизайнеров.

Создателем Git'а является [Линус Торвальдс](https://ru.wikipedia.org/wiki/Торвальдс,_Линус).

С помощью Git-a вы можете откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий.

Репозиторием называют хранилище вашего кода и историю его изменений. Git работает локально и все ваши репозитории хранятся в определенных папках на жестком диске.

## Создание репозитория

Что бы создать(инициализировать) новый репозиторий в текущей папке нужно в термнале ввести команду:

    git init

## Проверка состояния репозитория

Что бы проверить состояние репозитория нужно в терминале ввести команду:

    git status

## Добавление версионности

Для того чтобы начать отслеживать (добавить под версионный контроль) новый файл нужно в терминале ввести команду:

    git add <имя файла>

## Сравнивание двух различных коммитов

Что бы понять, чем отличается текущий файл от того что сохранено(закомичено), нужно ввести команду:

    git diff<номер файла>

## Журнал изменений

Что бы узнать все изменения в репозиторие, нужно в терминале ввести команду:

    git log

Что бы показать все изменения репозитория в одну строку
нужно в терминале ввести команду:

    git log --oneline

## Перемещение между ветками

Что бы перемещаться между ветками репозитория нужнр в терминале ввести команду:

    get checkout <адрес>

# Работа с ветками

Ветка представляет собой отдельное направление разработки. Ветки выступают в качестве абстрактного представления для процесса редактирования/индексации/коммита. Можно рассматривать их как способ запросить новый рабочий каталог, раздел проиндексированных файлов и историю проекта. Новые коммиты записываются в историю текущей ветки, что приводит к образованию развилки в истории проекта.

## Создание новой ветки

Чтобы создать новую ветку в репозитории нужно ввести команду:
    
    git branch <имя ветки>

## Просмотр всех веток

Чтобы посмотреть все созданные ветки в репозитории и узнать на какой из веток вы находитесь(ветка будет выделена *ЗЕЛЕНЫМ*) используется команда 

    git branch

![Пример](22.PNG)

## Слияние веток

Для того что бы сделать слияние веток, нужно ввести команду:

    git merge <название ветки, которую хотите влить>

- **ВАЖНО!**

Нужно находиться на той ветке, с которой собираетесь делать слияние!

## Удаление веток

Чтобы удалить ветку в репозитории, нужно ввести команду:

    git branch -d <название ветки>

- **ВАЖНО!** 

Если в ветке присутствуют несмерженные(merge) изменения или незапушенные коммиты, флаг -d не позволит удалить такую локальную ветку.

Это связано с тем, что эти коммиты нигде более не отслеживаются, и Git защищает вас от случайной потери этих данных.

Чтобы принудительно удалить ветку в репозитории, нужно ввести команду:

    git branch -D <название ветки>
    
# Добавление ссылок и картинок

## Ссылки

Чтобы в репозиторий вставить ссылку, нужно в VSCode ввести

    [Название](Ссылка)

- Пример: [Работа с Git](https://git-scm.com/docs/user-manual)

## Картинки

Чтобы в репозиторий вставить картинуку, нужно в VSCode ввести:

    ![Название](Имя картинки с ее разрежением)

- Пример:

![Вася](33.jpg)



## Создание репозитория на Githab (Есть уже локальный репозиторий, нужно сделать его копию на Githab'е).
![Githab](1.png)

1. Прежде чем начать пользоваться сайтом, нужно авторизоваться.
2. Жмем на иконку New, как указано на картинке:
![New](2.jpg)
3. Откроется страница для создания на которой будет указан Ваш логин.
Рядом будет строка для ввода имени репозитория.
Так же можно будет добавить доп. описание и выбрать каким будет Ваш репозиторий - публичным или приватным.
Внизу страницы будет кнопка для создания репозитория - Create Repozitory.
![Страница создания репозитория](3.PNG)
4. Репозиторий создан. Дальше Githab дает подсказки что можно сделать с эти репозиторием:
- ... или создайте новый репозиторий в командной строке
- ... или отправьте существующий репозиторий из командной строки
- ... или импортировать код из другого репозитория
![Варианты дальнейшей работы](4.PNG)
5. Выбираем второй вариант. В VSCode открываем папку в которую собираетесь *запушить* этот репозиторий. В терминале вводим команды из этого варианта:  

        git remote add origin https://github.com/BaydJi/Dlya_DZ.git
        git branch -M main
        git push -u origin main

    **Принять к сведению!** - Если уже есть своя основная ветка *master*, то во второй и третьей строке можно вместо *main*, ввести ее название.
6. При первом вводе этих команд VSCode потребует авторизацию с Githab:
![Авторизация](5.jpg)

    После чего возвращаемся на Githab, обновляем страницу и видим что появился наш локальный репозиторий(создана копия локального репозитория на Githab'е).

## В репозитории на Githab'е так же можно вносить изменения и комитить действия.
Чтобы этот комит появился в локальном репозитории нужно в терминале ввести команду:

    git pull

Чтобы изменения в локальном репозитории появились на Githab'е нужно в терминале ввести команду

    git push

# Копирование удаленного(чужого) репозитория.

1. В VSCode или на рабочем столе(как удобно) создем новую папку.

2. Чтобы *форкнуть* чужой репозиторий в Githab'е прожимаем иконку Fork в правом верхнем углу:
![Пример Fork](6.jpg)

3. Появляется новое окно:
![Create a new fork](7.jpg)

    Здесь мы можем дать свое название репозиторию.
    Прожимаем кнопку Create fork. Происходит копирование репозитория из одной учетной записи в другую учетную запись(Вашу), в которую вас автоматом перекинет.
4. Чтобы начать работать с этим репозиторием локально, его нужно скопировать. Жмем на зеленую кнопку с надписью Code:
![Code](8.PNG)

    В открывшемся окне копируем HTTPS:
    ![HTTPS](9.PNG)
5. Далее в терминале нужно ввести команду:
        
        git clone <адресс репозитория>

    После этой команды, в папке, которую мы создали появится папка с репозиторием, который мы скопировали.

    **ВАЖНО!** - В этот момент мы находимся в папке, которую создавали в самом начале(в ней нет репозитория). Для дальнейшей корректной работы нам нужно перейти в папку, которая появилась после копирования чужого репозитория. Для этого в терминале нужно ввести команду:

        cd <имя папки в которую собираемся перейти>


## При работе с чужим репозиторием.

При работе с чужим репозиторием не принято это все делать в ветке *master*. Нужно создать новую ветку, в которой будем вносить свои изменения.

После внесенных изменений их нужно запушить уже известной нам командой:

    git push

После ввода этой команды репозиторий выдаст ошибку:
![Error](10.jpg)

Git выдаст ошибку. Для дальнейше корректной работы в терминале вводим команду, которую предлагает нам Git:

    git push --set-upstream origin remoted

После ввода этой команды терминал отчитается как все прошло, после чего повторно вводим команду:

    git push

## Завершение.

После того как мы все запушили, переходим на Githab, прожимаем иконку с ветками и видим там созданную нами ветку. Открываем ее:
![Проверка пуша на githab](11.jpg)

На открывшейся страницe мы видим всю нашу проделанную работу и все наши комиты.
Прожимаем кнопку Contribute и в открывшемся окне прожимаем зеленую кнопку Open pull request.
![Open pull request](12.PNG)
 
**И финал!** - На открывшейся странице прожимаем все так же зеленую кнопку Create pull request:
![Finish](13.PNG)

После этого все внесенные нами изменения в чужом репозитории отправлены исходному владельцу. С ними он уже сможет ознакомиться.