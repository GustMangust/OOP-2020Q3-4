# Лабораторная работа № 1. 
## Вопросы

1. Что такое система контроля версий, для чего ее используют? <br>
Система управления версиями — программное обеспечение для облегчения работы с изменяющейся информацией. Система управления версиями позволяет хранить несколько версий одного и того же документа, при необходимости возвращаться к более ранним версиям, определять, кто и когда сделал то или иное изменение, и многое другое.
2. Какой принцип хранения файлов использует Git? <br>
Git к хранению данных больше похож на набор снимков миниатюрной файловой системы. Каждый раз, когда вы делаете коммит, то есть сохраняете состояние своего проекта в Git, система запоминает, как выглядит каждый файл в этот момент, и сохраняет ссылку на этот снимок. Для увеличения эффективности, если файлы не были изменены, Git не запоминает эти файлы вновь, а только создаёт ссылку на предыдущую версию идентичного файла, который уже сохранён. Git представляет свои данные как, скажем, поток снимков.
3. В чем отличие git от других систем контроля версий? <br>
Основное отличие Git от любой другой СКВ — это подход к работе со своими данными.
4. В каких трех основных состояниях файлы могут находиться в Git ?
* неизменённое (unmodified)
* изменённое (modified)
* подготовлено к коммиту (staged)
5. Что такое индексация файла? Какой командой она выполняется? <br>
Это означает, что git теперь знает об изменении, но изменение пока не перманентно (читай, навсегда) записано в репозиторий. Следующий коммит будет включать в себя проиндексированные изменения. <br>
$ git add
6. Что такое фиксация файла? Какой командой она выполняется? <br>
Простейший способ зафиксировать изменения. Позволяет фиксировать измененные файлы, которые индексируются в текущий момент. При фиксации можно написать комментарий к этому действию. <br>
$ git commit 
7. Продемонстрируйте команду проверки выбранных настроек. <br>
$ git config --list <br>
8. Как инициализировать репозиторий в существующей папке?
```
cd project_path
git remote add origin git@yiur_repo.git
git push -u origin master
```
9. Как указать файлы, за которыми должна следить система? <br>
$ git add <br>
10. Как выполнить фиксацию изменений? <br>
$ git commit <br>
11. Какой командой определить состояния файлов? <br>
$ git status <br>
12. Для чего создается файл .gitignore?Поясните его структуру. <br>
.gitignore служит для указания в нём файлов и папок, которые необходимо скрыть от системы контроля версий git. <br>
Как правило, скрывают файлы или папки, которые автоматически генерируют своё содержимое, либо имеют конфигурационные параметры, которые могут различаться у тех, кто совместно работает над проектом. <br>
13. Как используется команда git diff? <br>
Команда git diff используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей директорией и индексом (собственно git diff), разница между индексом и последним коммитом (git diff --staged), или между любыми двумя коммитами (git diff master branchB). <br>
14. Как используется команда git commit? <br>
Команда git commit берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок. <br>
15. Как используется команда git log? Какие у нее есть параметры? <br>
Команда git log выводит в обратном хронологическом порядке список сохраненных в данный репозиторий версий. -p, который показывает дельту (разницу/diff), привнесенную каждым коммитом. -[<число>] - покажет лишь последнее [<число>] коммитов <br>
16. Как используется команда git commit –amend? <br>
Это удобный способ изменить последний коммит. Она позволяет объединить проиндексированные изменения с предыдущим коммитом без создания нового коммита. <br>
17. Как отобразить удаленные репозитории? <br>
Для того, чтобы просмотреть список настроенных удалённых репозиториев, вы можете запустить команду git remote <br>
18. Как извлечь данные из удаленного репозитория? <br>
$ git remote add <shortname> <url>: <br>
19. Как отправить данные в удаленный репозитроий? <br>
$ git push <remote-name> <branch-name> <br>
20. Какая команда позволяет отобразить удаленные репозитории, 
связанные с текущим локальным? <br>
$ git remote (-v) <br>
21. Каким образом можно получить изменения из удаленного
репозитория в локальный? <br>
$ git fetch и $ git pull <br>
22. Для чего используется команда fetch? В чем отличие команды fetch
от pull? <br>
git fetch получает изменения с сервера и сохраняет их в каталог. Это никак не влияет на локальные ветки и текущие изменения. А git merge уже вливает все эти изменения в локальную копию. <br>
git pull — это, по сути, команда git fetch, после которой сразу же следует git merge. <br>
23. Для чего используется команда merge? В чем отличие merge от
rebase? <br>
Merge используется для слияния двух веток. При использовании rebase у нас не создаётся и не сохраняется отдельная ветка в которой были изменения, т.е. перезаписывается истории. При этом все изменения сжимаются в один патч и вносятся в целевую ветку. <br>
24. Что такое pull request? <br>
Это запрос к управляющему каким-либо репозиторием (человеку, группе людей или вообще роботу) на применение изменений (из вашего репозитория и/или указанной вами ветки). <br>
25. Какая команда позволяет отобразить историю репозитория? <br>
$ git log <br>
26. Продемонстируйте создание новых веток в Git? Что такое
ветвление? Что такое указатель HEAD? <br>
$ git branch [<branch>] для создания ветки. Ветка — это отдельное место для реализации новых идей. Изменения в ветке не затронут основную ветку master до тех пор, пока вы сами этого не захотите. Head - это указатель на текущую ветку или коммит ( на котором вы находитесь). <br>
27. Как используется команда git checkout? <br>
git checkout [<branch>] - позволяет переключаться между ветками репозитория <br>
28. Как выполнить включение изменений из одной ветки в другую? <br>
Использовать слияние веток - git merge  <br>
29. Какие проблемы могут быть при слиянии и как они разрешаются? <br>
Есть две ветки. в каждой из них присутствует файл который редактировался (один и тот же). При слиянии веток произойдет конфликт слияния (merge conflict) и его нужно будет как-то разрешить. Разрешить конфликт можно вручную выбрав одну из двух версий файла. <br>
30. Что такое GitLab? <br>
GitLab — это сервис, похожий на github, который организации могут использовать для обеспечения внутреннего управления git-репозиториями. Это самостоятельная система управления Git-репозиторием, которая хранит пользовательский код в секрете и может легко внедрять изменения кода.
