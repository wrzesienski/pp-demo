# pp-demo
## настройка окружения (пример для macOS)
устанавливаем python3 на локальный хост, пример ниже для macOS и homebrew
```
brew install python3
```
после этого в локальном проекте создаем локальное python окружение
```
python3 -m venv venv
``` 
переключаемся на локальное окружение
```
source venv/bin/activate
```
устанавливаем python либы
```
pip install -r requirements.txt
```
## настройка кред

В файле inv.yml настраиваем имя пользователя `ansible_user`, через которого будет осуществляться подключение.
Там же можем настроить пароль `ansible_password`.  
Или, если логин осуществляется через rsa, то добавляем в ssh-agent ключ для подключения
```
ssh-add path/to/developer_id_rsa
```  

Указываем хост подключения `ansible_host`.

## запуск плейбука
согласно тз, в плейбуке последовательно происходит первичная настройка ОС и установка соответствующих тулзов.
Запуск плейбука
```
ansible-playbook -i inv.yml playbook.yml --ask-vault-pass
```