# Cisco IOS Cheat Sheet

Минималистичный справочник команд для настройки коммутаторов и маршрутизаторов в Cisco Packet Tracer.

## Содержание

1. [Базовая настройка и SSH](./01-basic-ssh.md)
2. [VLAN, Trunk, DTP и VTP](./02-vlan-trunk-vtp.md)
3. [EtherChannel (LACP / PAgP)](./03-etherchannel.md)
4. [Безопасность портов (Port-Security, DHCP Snooping, DAI)](./04-port-security.md)
5. [Маршрутизация OSPF](./05-ospf.md)

## Быстрая проверка (Show)

```ios
show vlan brief                      ! Список VLAN и назначенных портов
show int trunk                       ! Активные транки
show vtp status                      ! Статус VTP
show etherchannel summary            ! Состояние Port-Channel
show port-security int fa0/1         ! Статус Port-Security на порту
show ip dhcp snooping binding        ! Таблица привязок IP-MAC
show ip ospf neighbor                ! Соседи OSPF
show ip route                        ! Таблица маршрутизации
show running-config                  ! Текущая конфигурация
```