# Маршрутизация OSPF

[← Назад к оглавлению](./README.md)

## Базовая настройка (Single-Area)

```ios
router ospf 1
 router-id 1.1.1.1
 network 192.168.10.0 0.0.0.255 area 0
 passive-interface g0/0                              ! Отключить Hello-пакеты в сторону локальной сети
 exit
```