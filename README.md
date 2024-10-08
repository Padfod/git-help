# git-help
Git commands/ theory + terminal


Узнать, где вы сейчас, позволяет команда pwd. Расшифровывается как Print Working Directory – покажи рабочую папку.
ls - то сокращение от list directory contents — «вывести список содержимого каталога».
Чтобы переместиться из одной папки в другую, пользуйтесь командой cd.
Команда mkdir создаёт папку.
Создадим нужные файлы. Это делают командой touch, от английского слова touch — прикоснуться, и вы будто создаёте файл прикосновением, передавая ей имя файла.
В командной строке для замены имени у нас есть команда mv, от английского move — двигать.


Удаление папок и файлов

Для удаления файлов используют команду rm, от английского remove — удалять: rm bad-emotions.txt
Удалить папку можно командой rmdir: rmdir images # удалит папку images из текущей папки
Но если в папке, которую вы пытаетесь удалить, есть какие-то файлы, командная строка не удалит её и выведет сообщение, что папка не пуста.

Удаление папок и файлов
Напоследок научимся удалять файлы и папки через командную строку.
Для удаления файлов используют команду rm, от английского remove — удалять:

rm bad-emotions.txt # удалит bad-emotions.txt из текущей папки
 

Удалить папку можно командой rmdir:

rmdir images # удалит папку images из текущей папки
 

Но если в папке, которую вы пытаетесь удалить, есть какие-то файлы, командная строка не удалит её и выведет сообщение, что папка не пуста:
Это защита от случайного удаления нужных файлов. Если папку всё-таки нужно удалить, можно использовать команду rm вот так:rm -r images # удалит папку images из текущей папки 

В этом случае -r называют ключом. Говорят: Мы вызвали команду rm с ключом r.
Команда rm -r удалит папку безвозвратно! Если вам хочется что-то удалить, но не уверены, воспользуйтесь командой перемещения mv или удаляйте с помощью корзины через графический интерфейс. Помните, что неосторожное выполнение команды может серьезно «сломать» проект или существующую программу.

Добавление содержимого файлов
Мы научились создавать файлы, но не умеем в них записывать текст. Тут нам пригодится команда echo. Сама команда не записывает данные в файл, она их лишь выводит.

Для записи в файл следует использовать символ перенаправления вывода — >>. Этот символ перемещает всё, что выводиться в командную строку, внутрь файла.
echo "Hello, practicum" 

Например, такая команда запишет строку “Hello, practicum” в файл: echo "Hello, practicum" >> practicum.txt 


Точно так же можно записывать вывод любой команды. Например, команда ниже запишет в файл current_dir.txt текущую
директорию:   pwd >> current_dir.txt 

Вывод содержимого файлов - cat output.txt 


Команда Описание
pwd - Показать текущую рабочую директорию (папку, из которой выполняетсякоманда).
ls - Отобразить файлы и папки в текущей директории.
l -a - Отобразить файлы и папки в текущей директории, в том числе скрытые.
cd first-project - Перейти в папку first-project .
cd first-project/test - Перейти в папку test внутри папки first-project .
cd .. - Перейти на уровень выше (в родительскую папку).cd ~ Перейти в домашнюю папку (например/Users/practicum ).
mkdir second-project - Создать папку second-project .
rm hello.txt - Удалить файл hello.txt .
rmdir images - Удалить папку images .
rm -r second-project - Удалить папку second-project и всё её содержимое.
touch hello.txt - Создать файл hello.txt в текущей папке.
touch hello.txt hello2.txt hello3.txt - Создать несколько файлов ( hello.txt , hello2.txt , hello3.txt ).
echo <текст> - Вывести текст на экран, например, echo "Hello, Practicum!"
echo <текст> >> <файл> - Вывести текст в файл, например, echo "Hello, Practicum!" >> output.txt .
cat practicum.txt - Вывести содержимое файла practicum.txt на экран.
cp helloPracticum.txt practicum.txt - Копировать файлы и папки. В этом примере информация из источника helloPracticum.txt скопируется в назначение practicum.txt .
mv <источник> <назначение> - Переместить/переименовать файлы и папки.
tail <файл> - Показать последние строки файла.
history - Показать историю введённых команд.
head <файл> - Показать первые строки файла.
man <команда> - Показать руководство по команде.
clear - Очистить экран терминала.
rm -rf ~/Library/Developer/Xcode/DerivedData - Удалить папку DerivedData Папка DerivedData обычно содержит
временные файлы, созданные Xcode в
процессе сборки и запуска проектов:
скомпилированные бинарные файлы,
индексы для ускорения поиска и
кэшированные данные. Удаление этой
папки может быть полезным, чтобы
освободить место на диске или решить
некоторые проблем, связанные с Xcode.
При следующем запуске Xcode
воссоздаст необходимые файлы в этой
папке.
Command K - очистка терминала (mac)
git --version - версия гита


Работа с файлом настройки .gitconfig
git config --global user.name "NAME"
git config --global user.email mail@mail.com
Теперь проверьте, что получилось.
git config --list
В ответ командная строка покажет ваши настройки:
user.name=NAME
user.email=mail@mail.com

Некоторые терминалы могут не просто распечатать список, а показать его во встроенном в терминал режиме просмотра текста. Выйти из просмотра настроек гита можно по клавише Q, от английского quit – покинуть, выйти.



По умолчанию git в macOS не чувствителен к регистру: если Git запомнил название файла как practicum.txt, то изменение его на PRACTICUM.txt не будет расценено как изменение. Это вызывает неудобства в Xcode, ведь разработчикам и разработчицам достаточно часто может понадобиться изменять названия файлов проекта.
Чтобы научить git быть внимательным к регистру, можно перенастроить его такой командой:

git config --global core.ignorecase false 

Вы можете сделать это сейчас, чтобы Git точнее отслеживал изменения в названиях файлов.

Сейчас мы познакомились с командой git config, к которой можно обращаться, чтобы перенастроить git.
Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием.
Для этого следует переместиться в неё и ввести команду git init (от англ. initialize — «инициализировать»).

    Если у вас нет папки для проектов, создайте её из консоли.
    И после этого давайте создадим папку с нашим проектом. Назовём его, например, first-project-git:
        mkdir first-project-git
        cd first-project-git 
    Теперь введите заветную команду, и обычная папка превратится в репозиторий: git init


Команда выведет сообщение вида: Инициализирован пустой репозиторий Git в <*ваша папка с проектом*>/.git/.
Внутри папки проекта (first-project-git) появилась новая папка .git, в ней хранится вся служебная информация. А её содержимое можно посмотреть с помощью команды ls .git:

    HEAD — текстовый файл с указанием, куда ведёт ссылка HEAD. Можно посмотреть содержимое этого файла, не выходя из консоли с помощью cat .git/HEAD.
    config — текстовый файл с настройками репозитория.
    description — текстовый файл с описанием репозитория.
    hooks — папка с хуками Git. Хуки — это специальные скрипты, которые можно выполнять перед различными действиями с гитом.
    info — папка с дополнительной информации о репозитории. Например, там есть файл exclude, в котором можно задавать пути до файлов и папок, которые игнорируются гитом. Однако этот механизм неудобен и чаще всего мы используем .gitignore — файлы о которых мы поговорим попозже.
    objects — папка с объектами Git. Советуем заглядывать туда почаще после внесённых изменений, чтобы лучше понять, что было сделано.
    refs — папка со ссылками, сокращение от английского references — ссылки. Содержит в себе ветки и прочие ссылки, о которых мы говорили ранее.


Мы не рассматриваем подробно служебную информацию из папки .git: при работе с задачами курса они вам не понадобятся.
Но если вы захотите погрузиться git ещё глубже, то всё самое интересное прячется именно здесь.
Команда git init — одна из редко применяемых, ведь репозиторий создаётся один раз, а пользоваться одним репозиторием можно сколько угодно долго.

«Разгитить» папку, если что-то пошло не так, — rm -rf .git
Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку .git.
    cd <папка с репозиторием> # перешли в папку
    rm -rf .git # удалили подпапку .git 

Разберём подробнее, что такое -rf:

    ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым, с этим ключом мы уже знакомы;
    ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».

Будьте осторожны: в подпапке .git хранится история изменений. Если удалить .git, то вся история проекта будет стёрта без возможности восстановления — останется только последняя версия файлов.

Состояние репозитория
Текущее состояние репозитория можно посмотреть с помощью команды git status:
    git status
Чтобы Git понял, что этот файл нужен для сохранения в новой версии, вводим git add и затем через пробел название файла:
    git add .
    git add fileName.fileFormat
    git add --all


Делаем первый коммит
Сделать коммит можно командой git commit с ключом -m(от англ. message – сообщение), который присваивает коммиту название.
Обычно в таком сообщении содержится пояснение, что именно было изменено. Названия нужны, чтобы найти полезную версию и посмотреть состояние репозитория на момент этого коммита.
Сделайте свой первый коммит, откройте консоль и вызовите команду: 
    git commit -m "Мой первый коммит!" 
    
    
    Работа с репами
    
    git remote add origin git@github.com:<ВАШ НИКНЕЙМ>/first-project-git.git 
    
Команду можно читать как «Git, добавь ссылку на удалённый репозиорий». Команда связывает локальный репозиторий с удалённым — или, проще говоря, сохраняет ссылку на страницу удалённого репозитория. Рассмотрим её подробнее:

    git remote add — команда для добавления нового удалённого репозитория.
    origin — короткое имя, которое мы присваиваем удалённому репозиторию. Origin — стандартное название для основного удалённого репозитория, но вы можете использовать любое другое.
    git@github.com:<ВАШ НИКНЕЙМ>/first-project-git.git — адрес удалённого репозитория на GitHub для SSH-подключения. Здесь <ВАШ НИКНЕЙМ> лучше заменить на реальный никнейм на GitHub, first-project-git — на название вашего репозитория на GitHub.

Эта команда выполняется один раз при настройке репозитория. Дальше git уже «запомнит», где находится удалённая версия, и вы сможете отправлять и получать изменения между локальным репозиторием и удалённым.
Следующую команду git branch -M main можно читать как «Git, возьми ветку и переименуй её в main». Ключ -M отвечает за переименование, а main — это название самой ветки.
Это действие обычно делается один раз, чтобы установить стандартное название для вашей основной ветки в проекте.
Мы упоминали, что каждый коммит сохраняет актуальное состояние файлов. Сами же коммиты хранятся в ветках (на английском — branches). Если коммит — это снимок состояния файлов, то ветка — временна́я шкала, на которой расположены эти снимки. Как с ними работать, рассмотрим в следующем уроке.

Выполним и разберём команду:
    git push -u origin main 
    git push — указывает Git отправить (или «запушить») изменения из вашего локального репозитория в удалённый. Как мы говорили до этого, push с английского — «толкать».
-u – этот ключ означает set upstream: мы устанавливаем связь между локальной веткой и удалённой. В следующий раз, когда вы будете отправлять или получать изменения, Git будет «знать», откуда брать или куда отправлять данные.
origin — название стандартного удалённого репозитория. Когда мы сохраняли ссылку на репозиторий командой git remote add, то использовали это короткое название для ссылки на репозиторий. Так Git «поймёт», что ветку нужно искать именно в репозитории с названием origin.
main — название ветки, которую вы хотите отправить в удалённый репозиторий. Пока что у нас одна ветка, но может быть больше — это тема отдельного урока.

Итак, всю команду git push -u origin main можно читать как «Git, отправь мои изменения из локальной ветки main в главную ветку удалённого репозитория (origin) и установи её как основную для будущих использований команды push».
После выполнения этих команд давайте убедимся, что Git выгрузил содержимое локального репозитория в GitHub-репозиторий:

Клонируем репозиторий и получаем изменения
Для этого у Git есть ещё одна команда — git clone; clone с английского — «клонировать».
    git clone git@github.com:<ВАШ НИКНЕЙМ>/ИМЯ-РЕПОЗИТОИЯ ПАПКАКУДА КЛОНИРОВАТЬ
cd ПАПКА КУДА КЛОНИРОВАЛИ
Разберём, как устроена команда:

    git clone — так объявляется команда Git для клонирования репозитория.
    git@github.com:<ВАШ НИКНЕЙМ>/first-project-git.git — адрес репозитория в GitHub, с которого вы хотите сделать копию.
    second-project-git — название папки на вашем компьютере, куда будет склонирован репозиторий. Если вы не укажете это название, Git создаст папку с тем же названием, что и у репозитория на GitHub — в нашем случае first-project-git. Нам этот вариант не подходит: у нас уже есть папка с названием репозитория в project.
    
    У Git есть и на это команда: git pull; а pull на английском — «тянуть».
Она противоположна команде git push: если первая выталкивала изменения в удалённый репозиторий, то git pull их вытягивает.


Команда git pull выполняет две основные операции:

    git fetch, которая скачивает изменения с удалённого репозитория,
    и git merge, которая объединяет эти изменения с вашей текущей рабочей версией.
    
        Перед выполнением git pull убедитесь, что ваша рабочая версия чиста, то есть все изменения зафиксированы: сделан commit.
    Иногда после выполнения git pull могут возникнуть конфликты слияния, если одни и те же части кода были изменены локально и в удалённом репозитории. В таком случае Git попросит вас разрешить эти конфликты перед тем как продолжить.
    
Ветки и Pull Requests
Что такое ветка
Ветка в Git — отдельный поток разработки. В таком потоке можно безопасно пробовать новые идеи и вносить изменения не влияя на основной код проекта.
С помощью веток разработчики и разработчицы могут работать над разными задачами параллельно и сохранять основную версию проекта стабильной. Это удобно как для командной работы, так и для индивидуальных проектов, позволяет легко переключаться между разными задачами и соединять новые функции, когда они готовы.
Прежде чем писать новую функциональность, для неё нужно создать отдельную ветку.
Основная, стабильная версия проекта хранится в главной ветке: main или master. Она появляется автоматически при создании репозитория. Часто все новые ветки в репозитории отходят от main, хотя это необязательно и можно встретить разные подходы.
Давайте посмотрим, какие команды нам доступны для работы с ветками.

    git branch — просматриваем ветки проекта
        
При вызове git branch выводятся ветки, которые есть в проекте. Звёздочкой (*) отмечено, в какой ветке вы находитесь сейчас.


    git branch <название_ветки>: создаём ветку
Перейдите в терминал и попробуйте создать новую ветку:
    $ git branch new_branch
    $ git branch # посмотрите список веток

    new_branch  # появилась новая
    * main   


Как назвать новую ветку?
Каждый и каждая выбирают свой подход к неймингу. Главное правило — название должно быть понятным всем участникам и участницам разработки.
Часто можно встретить в названии веток слова feature (англ. «особенность», «деталь») или bugfix (англ. bug — «жук», «ошибка» и fix — «исправить»), затем более подробное название на английском языке: feature/add_main_screen, bugfix/empty_background_image.
При работе с задачами на курсе мы будем использовать название спринта — sprint_03, sprint_04 и так далее.

    git checkout <название_ветки> - переключаемся между ветками
Затем сделайте коммит:
    git add . && git commit -m "Добавить git branch и git checkout в README"

Теперь ваш репозиторий выглядит так:
Вернитесь в главную ветку командой git checkout main и откройте файл README.md. В нём отобразится только первоначальный текст. Все изменения сохранились в ветку new_branch, а состояние главной ветки не изменилось.
Можно создать ветку и сразу начать в ней работать. За это отвечает команда git checkout с флагом -b (от англ. branch) и названием ветки. Эта команда делает то же самое, что и последовательность команд git branch <название_ветки> && git checkout <название_ветки>.
Убедитесь, что вы в основной ветке. Затем создайте ещё одну ветку another_branch и сразу переключитесь на неё.

$ git checkout main
$ git checkout -b another_branch # создали ветку и сразу на неё переключились
Switched to a new branch 'another_branch'

$ git branch
* another_branch # сразу в нужной ветке
  new_branch
  main 

Вот как теперь выглядит проект:
Сливаем ветки
Представьте, что закончили разработку новой функциональности в отдельной ветке и готовы объединить её с главной — добавить свои изменения в основную версию проекта. Этот процесс называется слиянием веток или мёрджем (англ. merge — «сливать», «поглощать»).
Перед тем как начать слияние, нужно перейти в ветку, куда должны добавиться изменения. Обычно это главная ветка. Перейдите в неё и вызовите команду git merge с именем присоединяемой ветки new_branch в качестве параметра.

$ git checkout main # переключились на главную ветку

$ git merge new_branch # объединили ветки
Updating 079cfbf..f30d441
Fast-forward
 README.md | 2 ++
 1 file changed, 2 insertions(+) 

Ветки объединены! Все коммиты из new_branch добавлены в главную ветку, Git перечислил изменённые файлы и количество изменённых строк в них.
После слияния веток main и new_branch репозиторий перейдёт в такое состояние:
Возвращаемся в GitHub
Допустим, вы закончили работу над задачей в локальной ветке. Теперь вы хотите, чтобы сначала изменения увидели ваши коллеги, а после — слить изменения с основной веткой. Для этого вам нужно переместиться в GitHub.
Обычно в основной ветке GitHub хранится актуальная версия проекта. Как правило, изменения сначала загружают в новую ветку и только потом вливают её в основную. Так коллеги смогут оценивать ваши правки до того, как те попадут в главную ветку.
Вы уже знаете команду git push: мы говорили, что она загружает изменения в удалённый репозиторий. Теперь скажем точнее: команда отправляет локальную ветку в удалённый репозиторий.
Откройте терминал и отправьте последние изменения из основной ветки в удалённый репозиторий:
git push -u origin main
💡 Команда для отправки локальной ветки в удалённый репозиторий называется push, поэтому разработчики и разработчицы так и говорят — «запушить».
Отлично! Теперь у нас есть актуальная версия проекта.
Убедитесь, что вы в основной ветке. Если нет — перейдите в неё через git checkout main, а затем создайте новую ветку merge-request и перейдите в неё (git checkout -b merge-request). Откройте файл README.md и добавьте туда строку о команде git merge:
С помощью команды git merge можно слить две ветки в одну.
Закомитьте изменения git add . && git commit -m "Добавить merge в README".
Чтобы отправить merge-request в удалённый репозиторий, ещё раз выполните команду push. Теперь необязательно переходить в ветку, чтобы запушить её:
git push -u origin merge-request
Откройте GitHub и обновите страницу. После добавления новой ветки произойдёт два события:

    Вместо 1 branch (англ. «одна ветка») станет 2 branches (англ. «две ветки»).
    По клику на список веток теперь можно перейти в ветку feature/merge-request.

А ещё GitHub предлагает вам создать какой-то Pull Request…
GitHub предоставляет удобный механизм, чтобы обсуждать новые изменения в ветках — Pull Request (англ. «запрос на изменения»; буквально: «запрос на подтягивание»). Обычно его так и называют – пулл-реквест, или сокращают до ПР или PR. 
Алгоритм такой:

    Вы делаете задачу в своей ветке. Когда заканчиваете работу, создаёте пулл-реквест.
    Ваши коллеги проверяют, что код выглядит аккуратно, логично и работа выполнена корректно. Они могут оставить комментарии, чтобы лучше понять решение или предложить, как сделать лучше. Этот процесс называется code review (англ. «рассмотрение кода») — или просто ревью.
    После финального обсуждения вы сливаете свою ветку в основную.

У каждого пулл-реквеста есть:

    Название — краткое описание изменений. Например: «Добавлены главный экран и подсчёт статистики».
    Описание — развёрнутое описание изменений. Это поле заполнять необязательно, но желательно.
    Исходная ветка — та, в которой вы работали. Например, merge-request.
    Целевая ветка — основная ветка проекта, в которую хотите внести изменения.

Где заполнять эти параметры, вы увидите дальше — в ходе тренировки.
Также у каждого пулл-реквеста может быть два исхода:

    Merge (англ. «соединить») — изменения приняты; код вливается в целевую ветку, пулл-реквест закрывается.
    Close (англ. «закрыть») — пулл-реквест закрывается без слияния изменений.

💡 Не путайте Git и GitHub – это два разных продукта.
Git – программа для терминала, с её помощью можно вести историю проекта. Её разработал Линус Торвальдс, Git распространяется с открытым исходным кодом.
GitHub — веб-сервис для хостинга репозиториев Git. Он облегчает совместную работу над проектами, предоставляет инструменты для управления версиями, отслеживания изменений и обсуждения проектов с другими разработчиками и разработчицами. GitHub принадлежит Microsoft.
Создание и мёрдж веток – инструменты программы Git. Механизм Pull Request – функция, предоставляемая платформой GitHub, который позволяет предлагать изменения и обсуждать их перед их интеграцией в основную ветку проекта.
Делаем Pull Request
Чтобы создать пулл-реквест для любой существующей ветки в GitHub, перейдите на страницу репозитория и выберите вкладку Pull requests в верхней части экрана.
Нажмите зелёную кнопку New pull request (англ. «новый запрос на изменения»).
Выберите названия веток:  ветка «куда» (в которую пулл-реквест будет осуществлён) и ветка «откуда» (из которой будет идти пулл-реквест). В нашем случае изменения должны попасть из ветки merge-request в ветку main.
В окне отобразятся добавленные коммиты и их изменения. Нажмите Create pull request.
Заполните поля с названием и описанием пулл-реквеста. Нажмите Create pull request.
Готово: пулл-реквест создан! Теперь вы или ваши коллеги могут перейти на вкладку Files changed (англ. «изменённые файлы»), чтобы оставить свои комментарии — провести ревью.
После ревью можно посмотреть комментарии и обсудить изменения на вкладке Conversations. Если вы захотите что-то добавить или исправить — можете в любой момент добавить дополнительные коммиты в ветку, они автоматически попадут в открытый пулл-реквест после пуша. Если вы работаете над задачей и исправляете её, обсудите детали с коллегами — тогда вы можете продолжать работать в одной ветке.
Осталось только нажать Merge pull request (англ. «принять запрос на изменения»). Это объединит ветку с вашими изменениями и ветку main.
Ура, теперь ваши изменения стали частью основной ветки!
Можете проверить результат, перейдя на главную страницу проекта и прочитав README.

