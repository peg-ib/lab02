# lab02
## PART 1.

Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.

$ cat > hello_world.cpp <<EOF

$ git add .

$ git commit -m "3rd"

Добавьте этот файл в локальную копию репозитория.
Закоммитьте изменения с осмысленным сообщением.
Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?
Запуште изменения в удалёный репозиторий.
Проверьте, что история коммитов доступна в удалёный репозитории.

$ nano hello_world.cpp

$ git add .

$ git commit -m "4th"

$ git push origin master

## PART 2.

В локальной копии репозитория создайте локальную ветку patch1.
Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.

$ git checkout -b patch1

$ nano hello_world.cpp

$ git add .

$ git commit -m "5th"

$ git push origin patch1

commit, push локальную ветку в удалённый репозиторий.
Проверьте, что ветка patch1 доступна в удалёный репозитории.
Создайте pull-request patch1 -> master.
В локальной копии в ветке patch1 добавьте в исходный код комментарии.

$ nano hello_world.cpp
 
$ git add .

$ git commit -m "6th"

$ git push origin patch1

Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
Локально выполните pull.
С помощью команды git log просмотрите историю в локальной версии ветки master.
Удалите локальную ветку patch1.

## PART3.

Создайте новую локальную ветку patch2.
Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.

$ git checkout -b patch2

$ clang-format -i -style=Mozilla hello_world.cpp

$ git add .

$ git commit -m "7th" 

$ git push origin patch2

commit, push, создайте pull-request patch2 -> master.
В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
Убедитесь, что в pull-request появились конфликтны.
Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.
Сделайте force push в ветку patch2
Убедитель, что в pull-request пропали конфликтны.
Вмержите pull-request patch2 -> master.
$ git pull

$ nano hello_world.cpp

$ git add .

$ git commit -m"8th"

$ git rebase master

$ nano hello_world.cpp

$ git add .

$ git rebase --continue

$ git pull origin master

$ git push -f origin patch2

Убедитель, что в pull-request пропали конфликтны.
