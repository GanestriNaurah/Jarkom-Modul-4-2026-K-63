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

## Konfigurasi Seluruh End Device

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

# CIDR

File project: [K-63-MODUL-4.pkt](https://drive.google.com/drive/folders/1q1XI-MlOwc5L_X5tm2rR5GYvjnwwIpdY?usp=sharing)

## Pembagian IP (hasil CIDR)

| Subnet | Network | Netmask | Keterangan |
|---|---|---|---|
| A1 | 10.95.28.0 | /25 | Cyberia - Switch (JJ, MyuMyu) |
| A2 | 10.95.28.128 | /30 | Cyberia - Wired |
| A3 | 10.95.4.0 | /29 | Switch tengah (Wired, Psyche, Copland, Schumann) |
| A4 | 10.95.27.0 | /30 | Wired - Navi |
| A5 | 10.95.19.128 | /30 | Wired - Tachibana |
| A6 | 10.95.0.0 | /22 | Psyche - Switch (Karl, Lin) |
| A7 | 10.95.14.0 | /26 | Copland - Juri |
| A8 | 10.95.12.0 | /23 | Copland - Switch (Masayuki) |
| A9 | 10.95.14.64 | /29 | Schumann - Akashic |
| A10 | 10.95.14.72 | /30 | Schumann - Accela |
| A11 | 10.95.8.0 | /22 | Accela - Switch (Omnipresence, Denpa) |
| A12 | 10.95.26.0 | /24 | Navi - Switch (Alice, Reika) |
| A13 | 10.95.25.0 | /26 | Navi - Switch (Taro) |
| A14 | 10.95.24.0 | /24 | Navi - Switch (Yasuo, Miho, Kuma) |
| A15 | 10.95.16.0 | /23 | Tachibana - Switch (Collective, Ghost) |
| A16 | 10.95.19.132 | /30 | Tachibana - Deus |
| A17 | 10.95.19.0 | /25 | Deus - Switch (Lilith, Specter) |
| A18 | 10.95.18.192 | /30 | Deus - Protocol7 |
| A19 | 10.95.18.128 | /26 | Protocol7 - Switch (Chisa, Hodgeson) |
| A20 | 10.95.18.16 | /30 | Protocol7 - Knights |
| A21 | 10.95.18.0 | /29 | Knights - Eiri |
| A22 | 10.95.18.8 | /30 | Knights - Phantoma |
| A23 | 10.95.18.32 | /27 | Phantoma - Switch (Semi) |
| A24 | 10.95.18.12 | /30 | Phantoma - Shibuya |
| A25 | 10.95.18.64 | /26 | Shibuya - Switch (Lain, Mika) |

## Konfigurasi router

### Cyberia

```
enable
configure terminal
hostname Cyberia
interface fa0/0
 description ke Switch JJ-MyuMyu
 ip address 10.95.28.1 255.255.255.128
 no shutdown
interface fa0/1
 description ke Cloud
 no ip address
 no shutdown
interface e1/0
 description ke Wired
 ip address 10.95.28.129 255.255.255.252
 no shutdown
exit
ip route 10.95.0.0 255.255.224.0 10.95.28.130
end
write memory
```

### Wired

```
enable
configure terminal
hostname Wired
interface fa0/0
 description ke Switch tengah
 ip address 10.95.4.1 255.255.255.248
 no shutdown
interface fa0/1
 description ke Navi
 ip address 10.95.27.1 255.255.255.252
 no shutdown
interface fa1/0
 description ke Tachibana
 ip address 10.95.19.129 255.255.255.252
 no shutdown
interface fa1/1
 description ke Cyberia
 ip address 10.95.28.130 255.255.255.252
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.28.129
ip route 10.95.0.0 255.255.252.0 10.95.4.2
ip route 10.95.12.0 255.255.252.0 10.95.4.3
ip route 10.95.8.0 255.255.252.0 10.95.4.4
ip route 10.95.14.64 255.255.255.240 10.95.4.4
ip route 10.95.24.0 255.255.252.0 10.95.27.2
ip route 10.95.16.0 255.255.252.0 10.95.19.130
end
write memory
```

### Psyche

```
enable
configure terminal
hostname Psyche
interface fa0/0
 description ke Switch tengah
 ip address 10.95.4.2 255.255.255.248
 no shutdown
interface fa0/1
 description ke Switch Karl-Lin
 ip address 10.95.0.1 255.255.252.0
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.4.1
end
write memory
```

### Copland

```
enable
configure terminal
hostname Copland
interface fa0/0
 description ke Switch tengah
 ip address 10.95.4.3 255.255.255.248
 no shutdown
interface fa0/1
 description ke Switch Masayuki
 ip address 10.95.12.1 255.255.254.0
 no shutdown
interface fa1/0
 description ke Juri
 ip address 10.95.14.1 255.255.255.192
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.4.1
end
write memory
```

### Schumann

```
enable
configure terminal
hostname Schumann
interface fa0/0
 description ke Switch tengah
 ip address 10.95.4.4 255.255.255.248
 no shutdown
interface fa0/1
 description ke Akashic
 ip address 10.95.14.65 255.255.255.248
 no shutdown
interface fa1/0
 description ke Accela
 ip address 10.95.14.73 255.255.255.252
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.4.1
ip route 10.95.8.0 255.255.252.0 10.95.14.74
end
write memory
```

### Accela

```
enable
configure terminal
hostname Accela
interface fa0/0
 description ke Schumann
 ip address 10.95.14.74 255.255.255.252
 no shutdown
interface fa0/1
 description ke Switch Omnipresence-Denpa
 ip address 10.95.8.1 255.255.252.0
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.14.73
end
write memory
```

### Navi (HWIC-4ESW, port `fa0/3/x`)

```
enable
vlan database
vlan 10
vlan 20
vlan 30
vlan 40
exit
configure terminal
hostname Navi
interface fa0/3/0
 description ke Wired
 switchport mode access
 switchport access vlan 10
interface fa0/3/1
 description ke Switch Alice-Reika
 switchport mode access
 switchport access vlan 20
interface fa0/3/2
 description ke Switch Taro
 switchport mode access
 switchport access vlan 30
interface fa0/3/3
 description ke Switch Yasuo-Miho-Kuma
 switchport mode access
 switchport access vlan 40
interface vlan 10
 ip address 10.95.27.2 255.255.255.252
 no shutdown
interface vlan 20
 ip address 10.95.26.1 255.255.255.0
 no shutdown
interface vlan 30
 ip address 10.95.25.1 255.255.255.192
 no shutdown
interface vlan 40
 ip address 10.95.24.1 255.255.255.0
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.27.1
end
write memory
```

### Tachibana

```
enable
configure terminal
hostname Tachibana
interface fa0/0
 description ke Wired
 ip address 10.95.19.130 255.255.255.252
 no shutdown
interface fa0/1
 description ke Deus
 ip address 10.95.19.133 255.255.255.252
 no shutdown
interface fa1/0
 description ke Switch Collective-Ghost
 ip address 10.95.16.1 255.255.254.0
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.19.129
ip route 10.95.18.0 255.255.254.0 10.95.19.134
end
write memory
```

### Deus

```
enable
configure terminal
hostname Deus
interface fa0/0
 description ke Tachibana
 ip address 10.95.19.134 255.255.255.252
 no shutdown
interface fa0/1
 description ke Protocol7
 ip address 10.95.18.193 255.255.255.252
 no shutdown
interface fa1/0
 description ke Switch Lilith-Specter
 ip address 10.95.19.1 255.255.255.128
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.19.133
ip route 10.95.18.0 255.255.255.0 10.95.18.194
end
write memory
```

### Protocol7

```
enable
configure terminal
hostname Protocol7
interface fa0/0
 description ke Deus
 ip address 10.95.18.194 255.255.255.252
 no shutdown
interface fa0/1
 description ke Switch Chisa-Hodgeson
 ip address 10.95.18.129 255.255.255.192
 no shutdown
interface fa1/0
 description ke Knights
 ip address 10.95.18.17 255.255.255.252
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.18.193
ip route 10.95.18.0 255.255.255.128 10.95.18.18
end
write memory
```

### Knights

```
enable
configure terminal
hostname Knights
interface fa0/0
 description ke Protocol7
 ip address 10.95.18.18 255.255.255.252
 no shutdown
interface fa0/1
 description ke Eiri
 ip address 10.95.18.1 255.255.255.248
 no shutdown
interface fa1/0
 description ke Phantoma
 ip address 10.95.18.9 255.255.255.252
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.18.17
ip route 10.95.18.0 255.255.255.128 10.95.18.10
end
write memory
```

### Phantoma

```
enable
configure terminal
hostname Phantoma
interface fa0/0
 description ke Knights
 ip address 10.95.18.10 255.255.255.252
 no shutdown
interface fa0/1
 description ke Shibuya
 ip address 10.95.18.13 255.255.255.252
 no shutdown
interface fa1/0
 description ke Switch Semi
 ip address 10.95.18.33 255.255.255.224
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.18.9
ip route 10.95.18.64 255.255.255.192 10.95.18.14
end
write memory
```

### Shibuya

```
enable
configure terminal
hostname Shibuya
interface fa0/0
 description ke Phantoma
 ip address 10.95.18.14 255.255.255.252
 no shutdown
interface fa0/1
 description ke Switch Lain-Mika
 ip address 10.95.18.65 255.255.255.192
 no shutdown
exit
ip route 0.0.0.0 0.0.0.0 10.95.18.13
end
write memory
```

## Konfigurasi node

Desktop > IP Configuration > Static.

| Node | IP | Netmask | Gateway |
|---|---|---|---|
| JJ | 10.95.28.2 | 255.255.255.128 | 10.95.28.1 |
| MyuMyu | 10.95.28.3 | 255.255.255.128 | 10.95.28.1 |
| Karl | 10.95.0.2 | 255.255.252.0 | 10.95.0.1 |
| Lin | 10.95.0.3 | 255.255.252.0 | 10.95.0.1 |
| Masayuki | 10.95.12.2 | 255.255.254.0 | 10.95.12.1 |
| Juri | 10.95.14.2 | 255.255.255.192 | 10.95.14.1 |
| Akashic | 10.95.14.66 | 255.255.255.248 | 10.95.14.65 |
| Omnipresence | 10.95.8.2 | 255.255.252.0 | 10.95.8.1 |
| Denpa | 10.95.8.3 | 255.255.252.0 | 10.95.8.1 |
| Alice | 10.95.26.2 | 255.255.255.0 | 10.95.26.1 |
| Reika | 10.95.26.3 | 255.255.255.0 | 10.95.26.1 |
| Taro | 10.95.25.2 | 255.255.255.192 | 10.95.25.1 |
| Yasuo | 10.95.24.2 | 255.255.255.0 | 10.95.24.1 |
| Miho | 10.95.24.3 | 255.255.255.0 | 10.95.24.1 |
| Kuma | 10.95.24.4 | 255.255.255.0 | 10.95.24.1 |
| Collective | 10.95.16.2 | 255.255.254.0 | 10.95.16.1 |
| Ghost | 10.95.16.3 | 255.255.254.0 | 10.95.16.1 |
| Lilith | 10.95.19.2 | 255.255.255.128 | 10.95.19.1 |
| Specter | 10.95.19.3 | 255.255.255.128 | 10.95.19.1 |
| Chisa | 10.95.18.130 | 255.255.255.192 | 10.95.18.129 |
| Hodgeson | 10.95.18.131 | 255.255.255.192 | 10.95.18.129 |
| Eiri | 10.95.18.2 | 255.255.255.248 | 10.95.18.1 |
| Semi | 10.95.18.34 | 255.255.255.224 | 10.95.18.33 |
| Lain | 10.95.18.66 | 255.255.255.192 | 10.95.18.65 |
| Mika | 10.95.18.67 | 255.255.255.192 | 10.95.18.65 |

## Pengujian

### Cek di router

```
show ip interface brief
show ip route
show cdp neighbors
show vlan-switch brief      (khusus Navi)
```

- Semua interface yang dipakai harus `up/up`.
- `show cdp neighbors` dipakai untuk mencocokkan kabel sebenarnya dengan IP yang terpasang.
- Di `show ip route`, baris `S*` adalah default route dan baris `S` adalah route summary.

### Ping antar router (dari CLI router, mode privileged)

```
Cyberia#   ping 10.95.28.130
Wired#     ping 10.95.27.2
Wired#     ping 10.95.19.130
Wired#     ping 10.95.4.2
Wired#     ping 10.95.4.3
Wired#     ping 10.95.4.4
Schumann#  ping 10.95.14.74
Tachibana# ping 10.95.19.134
Deus#      ping 10.95.18.194
Protocol7# ping 10.95.18.18
Knights#   ping 10.95.18.10
Phantoma#  ping 10.95.18.14
```

### Ping end-to-end dari Mika (Desktop > Command Prompt)

Urut dari yang terdekat ke terjauh, IP pertama yang gagal menunjukkan titik putusnya.

```
ping 10.95.18.65
ping 10.95.18.14
ping 10.95.18.13
ping 10.95.18.10
ping 10.95.18.9
ping 10.95.18.18
ping 10.95.18.17
ping 10.95.18.194
ping 10.95.18.193
ping 10.95.19.134
ping 10.95.19.133
ping 10.95.19.130
ping 10.95.19.129
ping 10.95.28.130
ping 10.95.28.129
ping 10.95.28.1
ping 10.95.28.2
```

### Ping Mika ke semua node

```
ping 10.95.28.2
ping 10.95.26.2
ping 10.95.25.2
ping 10.95.24.2
ping 10.95.0.2
ping 10.95.12.2
ping 10.95.14.2
ping 10.95.14.66
ping 10.95.8.2
ping 10.95.16.2
ping 10.95.19.2
ping 10.95.18.130
ping 10.95.18.2
ping 10.95.18.34
```

Node sisanya (satu subnet dengan node di atas):

```
ping 10.95.18.66
ping 10.95.18.131
ping 10.95.19.3
ping 10.95.16.3
ping 10.95.24.3
ping 10.95.24.4
ping 10.95.26.3
ping 10.95.8.3
ping 10.95.0.3
ping 10.95.28.3
```

### Menelusuri jalur

```
tracert 10.95.28.2
```

Hop terakhir yang membalas adalah router terakhir yang bekerja.

### Membaca hasil

| Hasil | Arti |
|---|---|
| `Reply from ...`, `Lost = 0` | Berhasil |
| `Lost = 1` di ping pertama | Wajar (ARP), ulangi sekali |
| `Request timed out` terus | Jalur putus, cek `show cdp neighbors` dan `show ip route` di router sepanjang jalur |
| `Destination host unreachable` | Router yang membalas tidak punya route ke tujuan |

### Gambar Pembagian IP
<img width="3157" height="1795" alt="Lingkaran CIDR - Topologi CPT" src="https://github.com/user-attachments/assets/f0984282-bb1b-42fb-a806-ce694af2a601" />


<img width="2880" height="1360" alt="Pohon CIDR" src="https://github.com/user-attachments/assets/a65f8a6d-d2c6-4500-a70a-43e1a014c57c" />


