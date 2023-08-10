# git init - инициализировать репозиторий (создать репозиторий)

# git status - проверить статус гита

# git add <имя файла> добавить файл в staging area

# git add . добавить все файлы в staging area

# git commit -m 'Initial project version' закоммитить и написать сообщение

# git commit сделать коммит => затем тебя перебрасывает в редактор чтобы написать сообщение к коммиту=>написать сообщение коммита => press Esc => write :wq => press enter

# git clone https://github.com/libgit2/libgit2 - клонировать репозиторий

# git checkout README.md - откатиться к изменениям последнего коммита (если мы просто изменили файл)

# git restore --staged README.md - откатиться к фазе modified (красным цветом) (если мы нажали git add README.md) а затем можем прописать git checkout README.md
# git reset === равно верхнему случаю


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

# git reset HEAD <имя файла>

# git log -p -1 - посмотреть изменени, которые были сделаны в прошлом коммите

# git log --stat -1 - посмотреть информацию о коммите

# git log --pretty=oneline

# git log --pretty=format:"%h - %an, %ar : %s"

Полезные опции для git log --pretty=format отображает наиболее полезные опции для изменения формата.

# git log --oneline --since=2.weeks

<!-- -------------------------- -->

Следующим действительно полезным фильтром является опция -S, которая принимает аргумент в виде строки и показывает только те коммиты, в которых изменение в коде повлекло за собой добавление или удаление этой строки. Например, если вы хотите найти последний коммит, который добавил или удалил вызов определённой функции, вы можете запустить команду:

$ git log -S function_name
Последней полезной опцией, которую принимает команда git log как фильтр, является путь. Если вы укажете каталог или имя файла, вы ограничите вывод только теми коммитами, в которых были изменения этих файлов. Эта опция всегда указывается последней после двойного тире (--), чтобы отделить пути от опций:

$ git log -- path/to/file

Например, если вы хотите увидеть, в каких коммитах произошли изменения в тестовых файлах в исходном коде Git в октябре 2008 года, автором которых был Junio Hamano и которые не были коммитами слияния, вы можете запустить следующую команду:

$ git log --pretty="%h - %s" --author='Junio C Hamano' --since="2008-10-01" \
 --before="2008-11-01" --no-merges -- t/
5610e3b - Fix testcase failure when extended attributes are in use
acd3b9e - Enhance hold*lock_file_for*{update,append}() API
f563754 - demonstrate breakage of detached checkout with symbolic link HEAD
d1a43f2 - reset --hard/read-tree --reset -u: remove unmerged new paths
51a94af - Fix "checkout --track -b newbranch" on detached HEAD
b0ad11e - pull: allow "git pull origin $something:$current_branch" into an unborn branch
Из почти 40 000 коммитов в истории исходного кода Git, эта команда показывает только 6, которые соответствуют этим критериям.

<!-- ------------------ -->

# мы сделали коммит локально но хотим изменить или название коммита или содержание ?

# меняем код, который нужно изменить => git add . => git commit --amend => переходим в редактор => меняем название коммита => press Esc => :wq => press Enter

# git remote show origin - показаать информацию об удаленном репозиториии

# git remote add https://github.com/paulboone/ticgit - добавление удаленного репозитория

# git remote rename origin paul - поменять название удаленного репозитория с origin на paul

# git remote remove paul - удалить удаленный репозиторий

# git tag -l - посмотреть все теги существующие

# git tag -a v1.4 -m "my version 1.4" - создать tag

Обмен тегами
По умолчанию, команда git push не отправляет теги на удалённые сервера. После создания теги нужно отправлять явно на удалённый сервер. Процесс аналогичен отправке веток — достаточно выполнить команду git push origin <tagname>.

$ git push origin v1.5
Counting objects: 14, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (14/14), 2.05 KiB | 0 bytes/s, done.
Total 14 (delta 3), reused 0 (delta 0)
To git@github.com:schacon/simplegit.git

- [new tag] v1.5 -> v1.5
  Если у вас много тегов, и вам хотелось бы отправить все за один раз, то можно использовать опцию --tags для команды git push. В таком случае все ваши теги отправятся на удалённый сервер (если только их уже там нет).

$ git push origin --tags
Counting objects: 1, done.
Writing objects: 100% (1/1), 160 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To git@github.com:schacon/simplegit.git

- [new tag] v1.4 -> v1.4
- [new tag] v1.4-lw -> v1.4-lw
  Теперь, если кто-то клонирует (clone) или выполнит git pull из вашего репозитория, то он получит вдобавок к остальному и ваши метки.

  <!-- ----------------- -->

# git show v1.4 - посмотреть данные о теге

# git tag -a v1.2 -m 'add new tag' 12130cf - создать тег на определенном коммите

# git tag -d v1.2 - удалить определенный тег по названию

Обратите внимание, что при удалении тега не происходит его удаления с внешних серверов. Существует два способа изъятия тега из внешнего репозитория.

Первый способ — это выполнить команду git push <remote> :refs/tags/<tagname>:

$ git push origin :refs/tags/v1.4-lw
To /git@github.com:schacon/simplegit.git

- [deleted] v1.4-lw
  Это следует понимать как обновление внешнего тега пустым значением, что приводит к его удалению.

Второй способ убрать тег из внешнего репозитория более интуитивный:

$ git push origin --delete <tagname>

Как откатиться на определенный коммит и от него создать ветку?

# git checkout 12130cf - откатывается к нужному коммиту

# git checkout -b <имя ветки> - создаем ветку и переходим к ней

# Псевдонимы в Git

Прежде, чем закончить эту главу по основам Git, рассмотрим ещё одну маленькую хитрость, которая поможет сделать использование Git проще, легче, и более привычным: псевдонимы (aliases). Мы не будем ссылаться на них дальше или предполагать, что вы будете пользоваться ими по ходу чтения книги, но вам лучше было бы знать, как их использовать.

Git не будет пытаться сделать вывод о том, какую команду вы хотели ввести, если вы ввели её не полностью. Если вы не хотите печатать каждую команду для Git целиком, вы легко можете настроить псевдонимы (alias) для любой команды с помощью git config. Вот несколько примеров псевдонимов, которые вы, возможно, захотите задать:

$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
Это означает, что, например, вместо ввода git commit, вам достаточно набрать только git ci. По мере освоения Git вам, вероятно, придётся часто пользоваться и другими командами. В этом случае без колебаний создавайте новые псевдонимы.

Такой способ может также быть полезен для создания команд, которые, как вы думаете, должны существовать. Например, чтобы исправить неудобство, с которым мы столкнулись при исключении файла из индекса, можно добавить в Git свой собственный псевдоним unstage:

$ git config --global alias.unstage 'reset HEAD --'
Это делает эквивалентными следующие две команды:

$ git unstage fileA
$ git reset HEAD -- fileA
Такой вариант кажется немного более понятным. Также, обычно, добавляют команду last следующим образом:

$ git config --global alias.last 'log -1 HEAD'
Таким образом, можно легко просмотреть последний коммит:

$ git last
commit 66938dae3329c7aebe598c2246a8e6af90d04646
Author: Josh Goebel <dreamer3@example.com>
Date: Tue Aug 26 19:48:51 2008 +0800

    Test for current head

    Signed-off-by: Scott Chacon <schacon@example.com>

% --------------------

# git stash -

# git stash list

# git stash apply

# git stash drop

# git config --global core.editor "code --wait" - visual studio code with git

# git help

git config --global user.name “[firstname lastname]”
set a name that is identifiable for credit when review version history
git config --global user.email “[valid-email]”
set an email address that will be associated with each history marker
git config --global color.ui auto
set automatic command line coloring for Git for e

# git log branchB..branchA - show the commits on branchA that are not on branchB

git log --follow [file] - show the commits that changed file, even across renames

git diff branchB...branchA - show the diff of what is in branchA that is not in branchB

# git revert <commit> - Create new commit that undoes all of the changes made in <commit>, then apply it to the current branch.

# git reflog --all

git reset --hard - Reset staging area and working directory to match most recent commit and overwrites all changes in the working directory.


svkj;s;ckjfns'kld'knf;kbnsfjn'snfk'l