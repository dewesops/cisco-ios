# Базовая настройка и SSH

[← Назад к оглавлению](./README.md)

## Инициализация и пароли

```ios
enable
conf t
hostname SW-Lan1-3
no ip domain-lookup

enable secret cisco
service password-encryption
banner motd *NEED TO DO*

line console 0
 password pass
 login
 exec-timeout 0 0
 exit
```

## SSH v2

> Требует предварительно заданных `hostname` (не дефолтного) и `ip domain-name`.

```ios
ip domain-name ciscodomain.ru
crypto key generate rsa              ! Ввести: 1024
ip ssh version 2
username admin privilege 15 secret line

line vty 0 15
 transport input ssh
 login local
 exec-timeout 0 0
 exit

do wr
```

## IP-адрес коммутатора (SVI) и шлюз

```ios
int vlan 1
 ip address 10.16.200.1 255.255.255.224
 no shut
 exit

ip default-gateway 10.16.200.30
```