# ldap

## ДЗ
    

    1. Установить FreeIPA;
    2. Написать Ansible playbook для конфигурации клиента;
    3*. Настроить аутентификацию по SSH-ключам;
    4**. Firewall должен быть включен на сервере и на клиенте



Настройка клиента и сервера выполняется с помощью ansible 

Создание виртуальных машин и provisioning

    vagrant up 

ipa-server-install - Настройка сервера    
ipa-client-install - Подключение хоста к домену 

Также доступна аутентификацию по SSH, для входа на сервер необходимо выполнить:

    ssh -i ssh-key/id_rsa user@localhost -p 2200

![](https://github.com/MaxOOOOON/ldap/blob/main/pictures/Screenshot_20211025_011114.png)    



Firewall везде запущен
