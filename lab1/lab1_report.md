University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2024/2025  
Group: K34212  
Author: Elena Darovskikh  
Lab: Lab1  
Date of create: 29.09.2024  
Date of finished: 30.09.2024

## Лабораторная работа №1 "Установка CHR и Ansible, настройка VPN"

## <a name="section1">Описание</a>
Данная работа предусматривает обучение развертыванию виртуальных машин (VM) и системы контроля конфигураций Ansible а также организации собственных VPN серверов.

## <a name="section2">Цель работы</a>
Целью данной работы является развертывание виртуальной машины на базе платформы Microsoft Azure с установленной системой контроля конфигураций Ansible и установка CHR в VirtualBox.

## <a name="section4">Ход работы</a>

Для начала работы была создана виртуальная машина в Yandex Cloud на образе Ubuntu 22.04.
![image](https://github.com/user-attachments/assets/fbb31fc5-c5b4-4c9a-9ed4-efd1b870b1bb)
![image](https://github.com/user-attachments/assets/170052b0-b84c-4d4f-bf77-1b545cefa27d)

Далее были установлены необходимые компоненты: python, ansible.

![image](https://github.com/user-attachments/assets/553de4a5-33cf-4655-b814-26e1d66d39a1)

Затем был установлен VirtualBox а на него CHR (RouterOS).

![image](https://github.com/user-attachments/assets/4a1c0719-ad18-4492-8bb7-a68bef29f442)

Был выведен выданный ей ip-адрес.

![image](https://github.com/user-attachments/assets/147b0a35-56e7-484a-b6ef-6de2f1af5fbf)

Была запущена программма WinBox и выполнено подключение через выданный выше ip-адрес.

![image](https://github.com/user-attachments/assets/ad760647-70e6-444e-8671-88dfdbea5770)

В WinBox было настроено подключение WireGuard, где были указаны название и порт, а ключи сгенерировались автоматически.

![image](https://github.com/user-attachments/assets/89b8b2d7-bfcc-4f8c-8e4f-82604be142fa)

Также был добавлен адрес, который будет присвоен клиенту.

![image](https://github.com/user-attachments/assets/e86906a9-cc9d-4165-a79a-7ffcf8385cd9)

Далее была произведена настройка peer. Вставленный ключ - сгенерированный ключ при первоначальной настройке.

![image](https://github.com/user-attachments/assets/7b669367-aa00-46d5-8af9-d8edd69d2775)

На ВМ Ubuntu были сгенерированы ключи.

![image](https://github.com/user-attachments/assets/24e6ead5-0c30-4884-9c9a-e6c889be9c18)

Был создан конфигурационный файл для настройки сервера.

![image](https://github.com/user-attachments/assets/2b74ce93-29bc-480b-9794-7e2761490d5e)

## <a name="section5">Результаты/проверка</a> 

1. Проверка интернет соединения (ВМ Ubuntu)

   ![image](https://github.com/user-attachments/assets/36b0fdea-e1f6-49f4-b361-74d9ad890ae7)

2. Проверка интернет соединения (RouterOS)
   ![image](https://github.com/user-attachments/assets/0ba80ead-50c7-463c-8920-b2eee2ea3537)

3. Проверка связи между сервером и клиентом
   ![image](https://github.com/user-attachments/assets/4c827589-58ac-455a-bea0-b6d90b6be8c5)

## <a name="section6">Выводы</a> 

В ходе выполнения лабораторной работы была развернута виртуальная машина на платформе Yandex Cloud, а также на ней установлены Ansible и python. Была поднята вирутальная машина с CHR в VirtualBox. Был создан Wireguard сервер для организации VPN туннеля между ними.



