# Jarkom-Modul-4-2026-K-63

# VLSM 

## Konfigurasi Router

### Konfigurasi Cyberia

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
    address 10.95.16.57
    netmask 255.255.255.252
    gateway 10.95.16.58
    up echo 1 > /proc/sys/net/ipv4/ip_forward
    up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
    up iptables -A FORWARD -i eth1 -o eth0 -j ACCEPT
    up iptables -A FORWARD -i eth2 -o eth0 -j ACCEPT
    up iptables -A FORWARD -i eth0 -m state --state ESTABLISHED,RELATED -j ACCEPT

auto eth1
iface eth1 inet static
    address 10.95.14.1
    netmask 255.255.255.128

auto eth2
iface eth2 inet static
    address 10.95.16.61
    netmask 255.255.255.252
    up ip route add 10.95.0.0/19 via 10.95.16.62
```

### Konfigurasi Wired

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.62
    netmask 255.255.255.252
    gateway 10.95.16.61
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.16.65
    netmask 255.255.255.252

auto eth2
iface eth2 inet static
    address 10.95.16.69
    netmask 255.255.255.252

auto eth3
iface eth3 inet static
    address 10.95.16.33
    netmask 255.255.255.248

    up ip route add 10.95.14.0/25 via 10.95.16.61

    up ip route add 10.95.12.0/24 via 10.95.16.66
    up ip route add 10.95.15.64/26 via 10.95.16.66
    up ip route add 10.95.13.0/24 via 10.95.16.66

    up ip route add 10.95.10.0/23 via 10.95.16.70
    up ip route add 10.95.16.72/30 via 10.95.16.70
    up ip route add 10.95.14.128/25 via 10.95.16.70
    up ip route add 10.95.16.76/30 via 10.95.16.70
    up ip route add 10.95.15.128/26 via 10.95.16.70
    up ip route add 10.95.16.80/30 via 10.95.16.70
    up ip route add 10.95.16.48/29 via 10.95.16.70
    up ip route add 10.95.16.84/30 via 10.95.16.70
    up ip route add 10.95.16.0/27 via 10.95.16.70
    up ip route add 10.95.16.88/30 via 10.95.16.70
    up ip route add 10.95.15.0/26 via 10.95.16.70

    up ip route add 10.95.0.0/22 via 10.95.16.34
    up ip route add 10.95.8.0/23 via 10.95.16.35
    up ip route add 10.95.15.192/26 via 10.95.16.35
    up ip route add 10.95.16.40/29 via 10.95.16.36
    up ip route add 10.95.16.92/30 via 10.95.16.36
    up ip route add 10.95.4.0/22 via 10.95.16.36
```

### Konfigurasi Navi

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.66
    netmask 255.255.255.252
    gateway 10.95.16.65
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.12.1
    netmask 255.255.255.0

auto eth2
iface eth2 inet static
    address 10.95.15.65
    netmask 255.255.255.192

auto eth3
iface eth3 inet static
    address 10.95.13.1
    netmask 255.255.255.0
```

### Konfigurasi Tachibana

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.70
    netmask 255.255.255.252
    gateway 10.95.16.69
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.10.1
    netmask 255.255.254.0

auto eth2
iface eth2 inet static
    address 10.95.16.73
    netmask 255.255.255.252

    up ip route add 10.95.14.128/25 via 10.95.16.74
    up ip route add 10.95.16.76/30 via 10.95.16.74
    up ip route add 10.95.15.128/26 via 10.95.16.74
    up ip route add 10.95.16.80/30 via 10.95.16.74
    up ip route add 10.95.16.48/29 via 10.95.16.74
    up ip route add 10.95.16.84/30 via 10.95.16.74
    up ip route add 10.95.16.0/27 via 10.95.16.74
    up ip route add 10.95.16.88/30 via 10.95.16.74
    up ip route add 10.95.15.0/26 via 10.95.16.74
```

### Konfigurasi Deus

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.74
    netmask 255.255.255.252
    gateway 10.95.16.73
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.14.129
    netmask 255.255.255.128

auto eth2
iface eth2 inet static
    address 10.95.16.77
    netmask 255.255.255.252

    up ip route add 10.95.15.128/26 via 10.95.16.78
    up ip route add 10.95.16.80/30 via 10.95.16.78
    up ip route add 10.95.16.48/29 via 10.95.16.78
    up ip route add 10.95.16.84/30 via 10.95.16.78
    up ip route add 10.95.16.0/27 via 10.95.16.78
    up ip route add 10.95.16.88/30 via 10.95.16.78
    up ip route add 10.95.15.0/26 via 10.95.16.78
```

### Konfigurasi Protocol7

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.78
    netmask 255.255.255.252
    gateway 10.95.16.77
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.15.129
    netmask 255.255.255.192

auto eth2
iface eth2 inet static
    address 10.95.16.81
    netmask 255.255.255.252

    up ip route add 10.95.16.48/29 via 10.95.16.82
    up ip route add 10.95.16.84/30 via 10.95.16.82
    up ip route add 10.95.16.0/27 via 10.95.16.82
    up ip route add 10.95.16.88/30 via 10.95.16.82
    up ip route add 10.95.15.0/26 via 10.95.16.82
```

### Konfigurasi Knights

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.82
    netmask 255.255.255.252
    gateway 10.95.16.81
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.16.49
    netmask 255.255.255.248

auto eth2
iface eth2 inet static
    address 10.95.16.85
    netmask 255.255.255.252

    up ip route add 10.95.16.0/27 via 10.95.16.86
    up ip route add 10.95.16.88/30 via 10.95.16.86
    up ip route add 10.95.15.0/26 via 10.95.16.86
```

### Konfigurasi Phantoma

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.86
    netmask 255.255.255.252
    gateway 10.95.16.85
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.16.1
    netmask 255.255.255.224

auto eth2
iface eth2 inet static
    address 10.95.16.89
    netmask 255.255.255.252

    up ip route add 10.95.15.0/26 via 10.95.16.90
```

### Konfigurasi Shibuya

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.90
    netmask 255.255.255.252
    gateway 10.95.16.89
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.15.1
    netmask 255.255.255.192
```

### Konfigurasi Psyche

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.34
    netmask 255.255.255.248
    gateway 10.95.16.33
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.0.1
    netmask 255.255.252.0
```

### Konfigurasi Copland

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.35
    netmask 255.255.255.248
    gateway 10.95.16.33
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.8.1
    netmask 255.255.254.0

auto eth2
iface eth2 inet static
    address 10.95.15.193
    netmask 255.255.255.192
```

### Konfigurasi Schumann

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.36
    netmask 255.255.255.248
    gateway 10.95.16.33
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.16.41
    netmask 255.255.255.248

auto eth2
iface eth2 inet static
    address 10.95.16.93
    netmask 255.255.255.252

    up ip route add 10.95.4.0/22 via 10.95.16.94
```

### Konfigurasi Accela

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 10.95.16.94
    netmask 255.255.255.252
    gateway 10.95.16.93
    up echo 1 > /proc/sys/net/ipv4/ip_forward

auto eth1
iface eth1 inet static
    address 10.95.4.1
    netmask 255.255.252.0
```

## KONFIGURASI SELURUH END DEVICE

#### Switch1

##### JJ
```
ip 10.95.14.2/25 10.95.14.1
save
```

##### Myumyu
```
ip 10.95.14.3/25 10.95.14.1
save
```

#### Switch3

##### Karl
```
ip 10.95.0.2/22 10.95.0.1
save
```

##### Lin
```
ip 10.95.0.3/22 10.95.0.1
save
```

#### Switch4

##### Masayuki
```
ip 10.95.8.2/23 10.95.8.1
save
```


#### Juri (langsung ke Copland)
```
ip 10.95.15.194/26 10.95.15.193
save
```


#### Switch5

##### Omnipresence
```
ip 10.95.4.2/22 10.95.4.1
save
```


##### Denpa
```
ip 10.95.4.3/22 10.95.4.1
save
```


#### Switch6

##### Alice
```
ip 10.95.12.2/24 10.95.12.1
save
```


##### Reika
```
ip 10.95.12.3/24 10.95.12.1
save
```


#### Switch7

##### Taro
```
ip 10.95.15.66/26 10.95.15.65
save
```


#### Switch8

##### Yasuo
```
ip 10.95.13.2/24 10.95.13.1
save
```


##### Miho
```
ip 10.95.13.3/24 10.95.13.1
save
```


##### Kuma
```
ip 10.95.13.4/24 10.95.13.1
save
```


#### Switch9

##### Collective
```
ip 10.95.10.2/23 10.95.10.1
save
```


##### Ghost
```
ip 10.95.10.3/23 10.95.10.1
save
```


#### Switch10

##### Lilith
```
ip 10.95.14.130/25 10.95.14.129
save
```


##### Specter
```
ip 10.95.14.131/25 10.95.14.129
save
```


#### Switch11

##### Chisa
```
ip 10.95.15.130/26 10.95.15.129
save
```


##### Hodgeson
```
ip 10.95.15.131/26 10.95.15.129
save
```

#### Switch12

##### Semi
```
ip 10.95.16.2/27 10.95.16.1
save
```


#### Switch13

##### Lain
```
ip 10.95.15.2/26 10.95.15.1
save
```


##### Mika
```
ip 10.95.15.3/26 10.95.15.1
save
```


#### Akashic (langsung ke Schumann)
```
ip 10.95.16.42/29 10.95.16.41
save
```


#### Eiri (langsung ke Knights)
```
ip 10.95.16.50/29 10.95.16.49
save
```

## PENGUJIAN

### Cek IP forwarding
```
cat /proc/sys/net/ipv4/ip_forward
```

Hasil harus `1`

### Tes Koneksi dalam Satu Subnet

#### JJ
```
ping 10.95.14.1
ping 10.95.14.3
```

#### Lin
```
ping 10.95.0.1
ping 10.95.0.2
```

#### Alice
```
ping 10.95.12.1
ping 10.95.12.3
```

### Tes Koneksi Antar Subnet

#### Karl
```
ping 10.95.12.2
ping 10.95.4.2
ping 10.95.14.2
ping 10.95.16.2
ping 10.95.10.2
```

#### JJ
```
ping 10.95.0.2
ping 10.95.13.2
ping 10.95.15.2
ping 10.95.16.2
```

#### Semi
```
ping 10.95.0.2
ping 10.95.4.2
ping 10.95.14.130
```

### Tes Komunikasi Lintas Cabang

#### JJ
```
ping 10.95.12.2
ping 10.95.13.2
ping 10.95.10.2
ping 10.95.4.2
ping 10.95.16.2
```

#### Karl 
```
ping 10.95.14.2
ping 10.95.15.2
ping 10.95.15.130
ping 10.95.16.42
```

#### Semi
```
ping 10.95.14.2
ping 10.95.12.2
ping 10.95.15.194
ping 10.95.4.2
```

### Tes Koneksi NAT

#### Cyberia
```
ping 8.8.8.8
```
```
ping google.com
```

#### Salah satu VPCS 
```
ip dns 8.8.8.8
ping 8.8.8.8
```

#### Salah satu Debian

```
nano /etc/resolv.conf
```

Isi:
```
nameserver 8.8.8.8
nameserver 1.1.1.1
```

```
ping google.com
```
