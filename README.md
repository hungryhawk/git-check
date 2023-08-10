# git init - инициализировать репозиторий (создать репозиторий)

# git status - проверить статус гита

# git add <имя файла> добавить файл в staging area

# git add . добавить все файлы в staging area

# git commit -m 'Initial project version' закоммитить и написать сообщение

# git commit сделать коммит => затем тебя перебрасывает в редактор чтобы написать сообщение к коммиту=>написать сообщение коммита => press Esc => write :wq => press enter

# git clone https://github.com/libgit2/libgit2 - клонировать репозиторий

# git checkout README.md - откатиться к изменениям последнего коммита (если мы просто изменили файл)

# git restore --staged README.md - откатиться к фазе modified (красным цветом) (если мы нажали git add README.md) а затем можем прописать git checkout README.md

# git branch -v - посмотреть последний коммит в ветке

# git branch - показать все ветки

## git branch --merged посмотреть те ветки, которые вы уже слили с текущей

## git branch --no-merged увидеть все ветки, содержащие наработки, которые вы пока ещё не слили в текущую ветку

# git branch -D <имя ветки> когда ты хочешь удалить какую-то ветку, при этом в ней есть изменения

# git branch <имя ветки> создать новую ветку

# git checkout <имя ветки> перейти на существующую ветку

# git log --oneline --decorate --graph --all посмотреть все коммиты в красивом виде

# git checkout -b <имя ветки> создать ветку и сразу на нее перейти

# git branch -D <имя ветки> когда ты хочешь удалить какую-то ветку, при этом в ней есть незакомиченные изменения

# git checkout <ветка, в которую нужно слить изменения> перейти в ветку, в которую собираешься сливать изменения

# git merge <ветка, из которой нужно взять изменения>

# git branch -d <имя ветки> удалить ветку

# git checkout <имя файла> - убрать изменения на стадии modified из определенного файла

# git checkout . - убрать изменения на стадии modified из всех файлов

# git branch --move <имя ветки, которое хочешь изменить> <новое имя ветки>

<!-- --------- -->

# git push --set-upstream origin <имя ветки> запушить на удаленный сервер созданную локальную ветку

# git branch --move <имя ветки, которое хочешь изменить> <новое имя ветки> меняем название ветки локально (в удаленном репозитории будет другое название)

# git push --set-upstream origin <новое имя ветки> запушить на удаленный сервер ветку с измененным названием (теперь на удаленном репозитории будет 3 ветки)

# git push origin --delete <имя ветки, которую хотим удалить в удаленном репозитории> теперь у нас 2 ветки локально и удаленно

<!-- -------------- -->

# git fetch origin - показать все удаленные ветки

# git checkout -b anton-0 origin/anton-0 - склонировать себе удаленную ветку

# git fetch origin - показать все удаленные ветки

# git merge origin/<имя ветки, данные которой хочешь склонировать себе в ветку>

# git status -s - показать статус в коротком виде

# git diff - показать подробнее какие произошли изменения (без добавления git add .)

# git diff --staged / git diff --cached - показать подробнее какие произошли изменения (c добавления git add .)

# git commit -a -m 'new message' - две команды в одной git add . + git commit -m 'new message'

когда мы хотим удалить файл
# rm script.js - когда он не проиндексирован (без git add script.js)

# git restore --staged script.js => rm script.js - когда он был проиндексирован (с git add script.js)

# git log -p -1 - посмотреть изменени, которые были сделаны в прошлом коммите

