# Домашнее задание к занятию 17.4 «Работа с roles» - Падеев Василий


![answer1]()
## Подготовка к выполнению

1. * Необязательно. Познакомьтесь с [LightHouse](https://youtu.be/ymlrNlaHzIY?t=929).  
2. Создайте два пустых публичных репозитория в любом своём проекте: vector-role и lighthouse-role.  
3. Добавьте публичную часть своего ключа к своему профилю на GitHub.  

## Основная часть

Ваша цель — разбить ваш playbook на отдельные roles. 

Задача — сделать roles для ClickHouse, Vector и LightHouse и написать playbook для использования этих ролей. 

Ожидаемый результат — существуют три ваших репозитория: два с roles и один с playbook.

**Что нужно сделать**

1. Создайте в старой версии playbook файл `requirements.yml` и заполните его содержимым:

   ```yaml
   ---
     - src: git@github.com:AlexeySetevoi/ansible-clickhouse.git
       scm: git
       version: "1.13"
       name: clickhouse 
   ```

2. При помощи `ansible-galaxy` скачайте себе эту роль.  
3. Создайте новый каталог с ролью при помощи `ansible-galaxy role init vector-role`.  
4. На основе tasks из старого playbook заполните новую role. Разнесите переменные между `vars` и `default`.   
5. Перенести нужные шаблоны конфигов в `templates`.  
6. Опишите в `README.md` обе роли и их параметры. Пример качественной документации ansible role [по ссылке](https://github.com/cloudalchemy/ansible-prometheus).  
7. Повторите шаги 3–6 для LightHouse. Помните, что одна роль должна настраивать один продукт.  
8. Выложите все roles в репозитории. Проставьте теги, используя семантическую нумерацию. Добавьте roles в `requirements.yml` в playbook.  

Создал 3 роли: APP (устанавливает git, node.js, npm, epel-release, nginx на виртуальную машину Lighthouse), Lighthouse и Vector
Добавил в [requirements.yml](https://github.com/Vasiliy-Ser/working_with_roles_17.4/blob/f471bca62ff61bffea270d681be2abdff8e74f43/playbook/requirements.yml)

9. Переработайте playbook на использование roles. Не забудьте про зависимости LightHouse и возможности совмещения `roles` с `tasks`.
Роли созданные мною выполняются без ошибок
![answer1](https://github.com/Vasiliy-Ser/working_with_roles_17.4/blob/f471bca62ff61bffea270d681be2abdff8e74f43/png/9.png) 
![answer1](https://github.com/Vasiliy-Ser/working_with_roles_17.4/blob/f471bca62ff61bffea270d681be2abdff8e74f43/png/10.png)
При выполнении роли clickhouse в задаче Install by YUM | Ensure clickhouse repo GPG key imported появляется ошибка. Требуется переменная которая указана для debian.  
![answer1](https://github.com/Vasiliy-Ser/working_with_roles_17.4/blob/f471bca62ff61bffea270d681be2abdff8e74f43/png/11.png)  

10. Выложите playbook в репозиторий.  
11. В ответе дайте ссылки на оба репозитория с roles и одну ссылку на репозиторий с playbook.  
[lighthouse-role](https://github.com/Vasiliy-Ser/ighthouse-role.git)  
[vector-role](https://github.com/Vasiliy-Ser/vector-role.git)  
[app-lighthouse-role](https://github.com/Vasiliy-Ser/app-lighthouse-role.git)  

