# То, что я вспомнил про изучение Git

## Что я делал

1. Скачал и установил Git
2. Задал некоторые конфигурационный параметры - свой логин и свой email
3. Создал у себя на компе папку с проектом
4. Инициализировал репозиторий командой git init в данной папке
5. Затем добавил туда нужный файлы
6. После чего можно проверить состояние репозитория командой git status
7. Для того, чтобы добавить файлы к "отслеживанию" нужно выполнить команду git add и название файла (или можно добавить все файлы например командой git add . или git add --all)
8. После выполнения можно сделать коммит командой git commit -m "И тут указать сообщение коммита (нужно указывать полезную информацию об изменении)"
9. Затем локальный репозиторий можно синхронизировать с github
10. Для этого должен быть зарегистрирован аккаунт, после чего нужно создать новый проект. (называть так же не обязательно, но будет проще)
11. Затем нужно сгенерировать ssh ключи и в настройках git-hub добавить свой публичный ключ
12. После чего нужно связать удаленный и локальный репозитории командой git remote add origin и адрес проекта из git-hub
13. После успешной связки можно "пушить" все изменения на удаленный репозиторий командой git push
14. Теперь при работе локально можно делать коммиты и пушить их в git-hub, где будет видна вся история изменений

## Дополнения по следующим пройденным темам:

1. Я прошел уроки по хешу коммита - это последовательность из определенных букв и цифр, которая уникально идентифицирует коммит.
2. Есть такое понятие как HEAD - по сути это файл, в папке .git, который содержит ссылку на файл, в котором содержится хеш последнего коммита
3. Так же боле детально разобрался в выводе команды git log и git log --oneline
   1. Первая команда выводит полную информацию о коммитах, а именно:
      * Первая строка это хеш коммита и указание HEAD, а так же название ветки
      * Вторая строка это информация об авторе - его Ник и адрес e-mail
      * Третья строка это дата создания коммита
      * В четвертой идет текст комментария коммита
   2. При использовании команды с ключем --oneline идет короткий вывод - по одной строке на каждый коммит:
      * Идет короткий вид хеша - при этом программа сама проверяет хеши всех коммитов в репозитории и выделяет такую длинну - чтобы это позволяло уникально идентифицировать коммит.
      * Далее идет указание HEAD, ветки и в конце текст комментария
      * Важный момент - в команде с данным ключем есть ограничение на количество символов в комментарии. Кажется это 34 или около того.
4. Также изучил информацию о возможных статусах файлов в Git репозитории
   1. Нужно чаще пользоваться командой git status для просмотра в каком состоянии находится репозиторий
      * Если есть измененные, неотслеживаемые или еще другие файлы - команда выдаст результат и даст подсказку по возможным действиям
   2. У файлов есть статусы:
      * untracked - это значит что Git знает о наличии этого файла, но никак не отслеживает его состояние и изменения
      * staged - это значит что Git отслеживает изменения этого файла, и он готов войти в коммит
      * modified - это значит что Git отслеживает файл, и в нем были выполнены изменения
        * Но тут может быть что файл изменен и готов к коммиту - тоесть staged
        * Или файл был изменен, но не включен в коммит командой git add

## Сейчас добавлю немного информации по тому, как нужно писать сообщения к коммитам

Текс сообщения к коммитам это важная часть в процессе работы. При работе с командой очень важно придерживаться определенных правил при написании сообщений в коммиты.
Если коротко - то можно выделить некоторые особенности:

* Сообщение должно быть не слишком длинным - часто в компаниях устанавливают минимальное и максимальное количество символов сообщения - например от 30 до 70
* Сообщение коммита должно быть информативным. Тоесть там должно быть указано что было изменено и где
* Так же часто принято указывать номера тикетов в jit - для автоматической привязки коммита к тикету
* Еще важно принять единообразный стиль написания таких сообщений - например в прошедшей форме, в настоящей и т.п. Будет ли оно начинаться с глагола, с номера тикета и т.п.

При наличии единообразного стиля и подхода к написанию сообщений коммитов - работать в команде будет гораздо проще и приятней