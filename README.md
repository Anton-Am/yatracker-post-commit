Yandex.Tracker Post Commit
======

Небольшой скрипт, который помогает дублировать комментарии из вашего гит коммита в задачах яндекс.трекера.

## Установка

1. Необходимо скопировать файл post-commit в корневую директорию `.git/hooks`. Если директории не существует, то необходимо
её создать.

2. После копирования необходимо запустить следующие команды:

`git config --global user.yatracker-token "ВАШ-OAUTH-ТОКЕН"`
(ВАШ-OAUTH-ТОКЕН: https://yandex.cloud/ru/docs/tracker/concepts/access#section_about_OAuth)

`git config --global user.yatracker-org "ВАШ-ИДЕНТИФИКАТОР-ОРГАНИЗАЦИИ"`
(ВАШ-ИДЕНТИФИКАТОР-ОРГАНИЗАЦИИ: https://tracker.yandex.ru/admin/orgs)

3. Опционально можно назначить следующий статус задачи и пользователя на которых будут переведены задачи с комментарием '[Закрыто]', '[Закрыл]', '[Тест]', '[Test]':

`git config --global user.yatracker-next-status "STATUS-NAME"`
(STATUS-NAME: https://tracker.yandex.ru/admin/statuses)

`git config --global user.yatracker-next-user-login "NEXT-USER"`
(NEXT-USER: https://tracker.yandex.ru/admin/users)

4. Меняем права на директорию:

`chmod 755 .git/hooks`

## Тестирование

```
1. Сделать коммит (Например: "Минорные исправления страницы О нас #WORK-719") 
2. WORK-719 - id вашей задачи в яндекс.трекере
3. Выполнить команду из корневой директории вашего проекта:

./.git/hooks/post-commit
```