University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2024/2025  
Group: K34212  
Author: Elena Darovskikh  
Lab: Lab3  
Date of create: 26.12.2024  
Date of finished: 27.12.2024

## Лабораторная работа №3 "Развертывание Netbox, сеть связи как источник правды в системе технического учета Netbox"

## <a name="section1">Описание</a>
В данной лабораторной работе вы ознакомитесь с интеграцией Ansible и Netbox и изучите методы сбора информации с помощью данной интеграции.

## <a name="section2">Цель работы</a>
С помощью Ansible и Netbox собрать всю возможную информацию об устройствах и сохранить их в отдельном файле.

## <a name="section4">Ход работы</a>

**Поднятие NetBox**
  
На ВМ в YandexCloud был поднят NetBox. Для этого последовательно были настроены база данных PostrgreSQL, Redis, NetBox, Gunicorn и HTTP сервер nginx.

Были установлены пакеты postrgresql.

```
sudo apt update
sudo apt install -y postgresql
```

Была создана база данных и настроен пользователь для допуска к ней.

<img src="./img/1.jpg" width=650>
  
Был проверен статус системы:

```
psql --username netbox --password --host localhost netbox
```
