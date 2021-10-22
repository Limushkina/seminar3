# Инструкция по работе с Git

## Что такое Git

**Git** - одна из реализаций распределенных систем контроля версий. Позволяет контролировать версионность файлов, как локально, так и на удаленном сервере. Самая популярная система контроля версий. 

## Подготовка репозитория

*Репозиторий* — это папка с Вашими документами, версиями которых управляет Git. 
Вы можете создать репозиторий из любой папки, за исключением тех из них, которые уже находятся под контролем версий Git. 
Создание нового репозитория в Git осуществляется с помощью команды *git init*. То есть инициализация - делает из папки репозиторий. 

## Создание "сохранений"

Создать "сохранения" они же фиксации или коммиты, мы можем с помощью комманды *git commit*. Для этого необходимо написать команду *git commit -m <сообщение к коммиту>. Сообщение к коммиту писать **ОБЯЗАТЕЛЬНО**. Все файлы должны быть отправленны в коммит с помощью команды *git add*. Если файлы не добавленны, то можно использовать флаг *-a* и команда приобретет вид *git commit -a -m <сообщение к коммиту*. 

## Журнал изменений

*Журнал изменений* — это файл, который содержит общий, хронологически упорядоченный список изменений, внесенных в проект. Он часто организован по версии с указанием даты, после чего следует список добавленных, переработанных и удаленных функций. Команда *git log* показывает журнал изменений, где отображается весь список коммитов, т.е. сохранений. 

## Перемещение между "сохранениями"

Для переключения между "сохранениями" (коммитами), необходимо использовать команду *git checkout* следующим образом *git checkout <номер коммита для переключения>*. Номер коммита берется из истории коммитов и на него произойдет переключение.

Команды *git reset* и *git revert* позволяют отменять коммиты. Команда *gti revert* возвращает к указанному коммиту, создавая новый коммит, а команда *git reset* возвращает к указанному коммиту и затирает историю изменений до указанного коммита. Применяется это следующим образом: *git revert <номер коммита>* или *git reset --hard <номер коммита>*.

## Ветки в Git

Ветка в Git — это простой перемещаемый указатель на один из коммитов. 

Команда *git branch* позволяет вывести список всех веток. Знак <*> показывает на какой ветке мы находимся. 

Команда *git checkout <name branch>* переключает на указанную ветку. 

Команда *git branch <name>* Создает новую ветку.

## Слияние веток и решение конфликтов

Для того, что бы перенести данные с ветки на которой мы находимся в главную ветку нужно использовать команду *get merge <name branch>*. После этой команды все данные будут хранится на главной ветке. 

Когда два человека изменяют одни и те же строки в файле или один разработчик удаляет файл, который в это время изменяет другой разработчик, возникает конфликт. В таких случаях Git не может автоматически определить, какое изменение является правильным. Git помечает файл как конфликтующий и останавливает процесс слияния. Самый простой способ разрешить конфликт — отредактировать конфликтующий файл. После редактирования файла выполните команду *git add*, чтобы добавить новое объединенное содержимое в раздел проиндексированных файлов. Для завершения слияния создайте новый коммит, выполнив следующую команду *git commit -m "Text message". Так же можно выбрать с какой ветки перенести и оставить информацию. 

## Удаление веток

Удалить ветку можно с помощью команды *git branch -d <name>*.

## Скачинвание удаленного репозитория

## Отправка изменений в удаленный репозиторий

Для отправки изменений в удаленный репозиторий мы используем команду *git push*. Тем самым отправляем все наши изменения на свой аккаунт на [GitHub](https://github.com). В окне на GitHub появляется возможность отправить *pull request*.
