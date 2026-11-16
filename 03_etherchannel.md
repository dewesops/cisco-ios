# EtherChannel

[← Назад к оглавлению](./README.md)

> Все порты в группе должны иметь одинаковую скорость, дуплекс и режим. Дальнейшие настройки вешаются на `int port-channel 1`.

## LACP (рекомендуется)

```ios
int range fa0/1-2
 shut
 channel-protocol lacp
 channel-group 1 mode active         ! active (инициатор) | passive (ожидание)
 no shut
 exit
```

## PAgP

```ios
int range fa0/1-2
 shut
 channel-protocol pagp
 channel-group 1 mode desirable      ! desirable (инициатор) | auto (ожидание)
 no shut
 exit
```

## Принудительно (Mode On)

```ios
int range fa0/1-2
 shut
 channel-group 1 mode on
 no shut
 exit
```

## Настройка логического интерфейса

```ios
int port-channel 1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,99
 exit
```