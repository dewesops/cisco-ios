# VLAN, Trunk, DTP и VTP

[← Назад к оглавлению](./README.md)

## Создание VLAN и Access-порт

```ios
vlan 10
 name Users
 exit

int fa0/1
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast              ! Только для портов с конечными устройствами (ПК)
 exit
```

## Trunk и DTP

```ios
int g0/1
 switchport mode trunk
 switchport trunk native vlan 99
 switchport trunk allowed vlan 10,20,99
 switchport nonegotiate              ! Отключить отправку DTP-пакетов
 exit
```

### Согласование DTP (опционально)

```ios
int g0/1
 switchport mode dynamic desirable   ! Вторая сторона: auto или desirable
 exit
```

## VTP

```ios
vtp domain ShvyrevLAN3BOTTOM
vtp password cisco
vtp version 2
vtp mode server                      ! server | client | transparent
```