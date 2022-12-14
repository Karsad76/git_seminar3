# **Инструкция по использованию системы контроля версий Git**

![картинка Git](git.jpeg)

## Что такое Git

Программа Git - это одна из самых популярных на сегодня систем контроля версий. Это консольная утилита для отслеживания и ведения истории изменения файлов в вашем проекте. Чаще всего его используют для программного кода, но можно и для других файлов.
Для отслеживания изменений Git использует локальный репозиторий, который хранит в скрытой папке <.git> в основной папке проекта.

Ниже приведены основные команды Git.

## Инициализация репозитория

Для создания нового репозитория используется команда:

    git init

Создается локальный репозиторий с одной веткой master в скрытой папке <.git> в текущей папке.

## Проверка состояния репозитория

Для проверки состояния репозитория используется команда:

    git status

## Добавление изменения в индекс

Для добавления изменения в индекс для следующего коммита используется команда:

    git add <filename>

## Сохранение индекса в репозиторий

Для сохранения в репозиторий индекса, созданного командой "git add", используется команда:

    git commit

Для добавления описания в коммите, команду можно использовать с параметром -m. Например так:

    git commit -m "message"

Команду "git add" для уже отслеживаемых файлов (не новых!) можно заменить командой "git commit" с параметром -a. Например:

    git commit -a

Также, с помощью параметров команды, можно объединить в одно действие индексацию отслеживаемого файла и его коммит с комментарием. Например:

    git commit -a -m "message"

или

    git commit -am "message"

Параметры команды можно указывать вместе, Git разберется))

## История коммитов

Для просмотра истории коммитов используется команда:

    git log

Для просмотра упрощенного списка коммитов (только хэш и комментарий), используется параметр "--oneline":

    git log --oneline

Для просмотра истории коммитов по всем веткам используется параметр "--all". Вот так:

    git log --all

или так:

    git log --oneline --all

## Просмотр изменений

Можно просматривать изменения файлов, внесённых в репозиторий, используя команду:

    git diff

Команда выводит изменения в рабочих файлах по сравнению с последним коммитом. 
Для сравнения коммитов между собой используют их хэши (из вывода команды "git log"). Вот так:

    git digg <commit1_hash> <commit2_hash>

## Переключение между коммитами

Для переключения между коммитами используется команда "git checkout" с параметром хэш коммита:

    git checkout <commit_hash>

## Ветвление

Ветвление в Git нужно для создания "параллельной реальности" и внесений изменений в исходный код не затрагивая основную ветку разработки. В Git ветвление - самый частоиспользуемый способ работы над проектом. Основной идеей ветвления является отклонение от основного кода и продолжение работы независимо от него. Также это удобно в тестировании отдельного функционала, потому что позволяет работать над новой частью кода, не беспокоясь о поломке чего-то в рабочей версии.

## Создание новой ветки

Для создания ветки используется команда:

    git branch <branch_name>

Создается новая ветка с именем <branch_name> от текущей ветки.

## Переход между ветками

Переход между ветками осуществляется с помощью команды:

    git checkout <branch_name>

Ветка <branch_name> становится текущей.

## Удаление веток

Для удаления ненужных веток используется команда:

    git branch -d <branch_name>

## Слияние

Для слияния веток необходимо использовать команду:

    git merge <branch_name>

При этом ветка <branch_name> вливается в текущую ветку.
Если конфликтов при слиянии веток Git не выявил, слияние пройдет в автоматическом режиме, после чего будет создан так называемый "коммит слияния" (коммит у которого два исходных "родителя").

## Конфликты при слиянии

При слиянии веток в Git возможно возникновение конфликта между разными версиями одного файла. Это происходит, когда один и тот же блок текста в разных ветках отредактирован по разному и Git не может сам определить какая версия корректная. В этом случае процесс слияния приостанавливается и Git предлагает пользователю разрешить конфликт самому. Автоматический коммит слияния при завершении объединения веток в таком случае не делается, сделать его надо в ручном режиме.

## Работа с удаленными репозиториями

Удаленный репозиторий - это... очень крутая штука

### Связь локального репозитория с удаленным

Для связи ...