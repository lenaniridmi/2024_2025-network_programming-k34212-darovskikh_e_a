University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2024/2025  
Group: K34212  
Author: Elena Darovskikh  
Lab: Lab2  
Date of create: 26.12.2024  
Date of finished: 27.12.2024

## Лабораторная работа №2 "Развертывание дополнительного CHR, первый сценарий Ansible"

## <a name="section1">Описание</a>
В данной лабораторной работе вы на практике ознакомитесь с системой управления конфигурацией Ansible, использующаяся для автоматизации настройки и развертывания программного обеспечения.

## <a name="section2">Цель работы</a>
С помощью Ansible настроить несколько сетевых устройств и собрать информацию о них. Правильно собрать файл Inventory.

## <a name="section4">Ход работы</a>

Был установлен второй CHR.

<img src="./img/1.jpg" width=650>

Была произведена настройка пользоватля admin и клиента WireGuard для поднятия  VPN соединения. Была сгенерирована вторая пара ключей при помощи следующей команды:

```
wg genkey | sudo tee /etc/wireguard/wg0-client2-private.key | wg pubkey | sudo tee /etc/wireguard/wg0-client2-public.key
```

На сервере в конфигурационный файл /etc/wireguard/wg0.conf был добавлен второй пир:

<img src="./img/2.jpg" width=650>

На CHR2 был добавлен интерфейс wireguard1 и назначен его ip-адрес, настроен пир и добавлено правило в firewall (разрешен трафик WireGuard).

```
/interface wireguard add listen-port=51820 mtu=1420 name=wireguard1
/interface wireguard peers add allowed-address=10.2.0.1/24 endpoint-address=158.160.53.43
endpoint-port=51820 interface=wireguard1 persistent-keepalive=10s
public-key="публичный ключ сервера"
/ip address add address=10.2.0.3/24 interface=wireguard1 network=10.2.0.0
/ip firewall filter add action=accept chain=input dst-port=51820 int-interface=wireguard1
protocol=udp
```
Дальше была проведена проверка связности виртуальных машин:

<img src="./img/3.jpg" width=650>

<img src="./img/4.jpg" width=650>
