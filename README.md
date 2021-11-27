# Jarkom-Modul-4-B11-2021

## **Kelompok B-11**

|      NRP       |         Nama          |
| :------------: | :-------------------: |
| 05111940000079 |    Muhammad Nevin     |
| 05111940000116 | Albert Filip Silalahi |
| 05111940000132 | Jagad Wijaya Purnomo  |

## Topologi
![soal](https://user-images.githubusercontent.com/31863229/142765592-e971b1a2-0214-4565-811a-87f083ecc4f3.PNG)

## CPT - VLSM
### Pembagian subnet
![c1](https://user-images.githubusercontent.com/31863229/142777462-03a67e5a-f0e3-4b3a-9223-b0ea659e6fc0.png)

### Perhitungan subnet
|Subnet|Jumlah IP|Netmask|
|------|---------|-------|
|A1|1001|/22|
|A2|2|/30|
|A3|701|/22|
|A4|2|/30|
|A5|2021|/21|
|A6|101|/25|
|A7|2|/30|
|A8|521|/22|
|A9|502|/23|
|A10|13|/28|
|A11|2|/30|
|A12|252|/24|
|A13|721|/22|
|**Total**|**5841**|**/19**|

### VLSM Tree
![c2](https://user-images.githubusercontent.com/31863229/142777556-b5c3fa17-f9bd-427e-8cc3-a38e27724d5d.png)

### Pembagian IP
|Subnet|Network ID|Netmask|
|------|----------|-------|
|A1|192.182.8.0|255.255.252.0|
|A2|192.182.0.0|255.255.255.252|
|A3|192.182.12.0|255.255.252.0|
|A4|192.182.0.4|255.255.255.252|
|A5|192.182.24.0|255.255.248.0|
|A6|192.182.0.128|255.255.255.128|
|A7|192.182.0.8|255.255.255.252|
|A8|192.182.16.0|255.255.252.0|
|A9|192.182.2.0|255.255.254.0|
|A10|192.182.0.16|255.255.255.240|
|A11|192.182.0.12|255.255.255.252|
|A12|192.182.1.0|255.255.255.0|
|A13|192.182.20.0|255.255.252.0|

### Routing
|Router|Subnet|Network ID|Netmask|Next Hop|
|------|------|----------|-------|--------|
|**FOOSHA**|A3|192.182.12.0|255.255.252.0|192.182.0.2|
||A5|192.182.24.0|255.255.248.0|192.182.0.2|
||A6|192.182.0.128|255.255.255.128|192.182.0.2|
||A8|192.182.16.0|255.255.252.0|192.182.1.10|
||A9|192.182.2.0|255.255.254.0|192.182.1.10|
||A10|192.182.0.16|255.255.255.240|192.182.1.10|
||A12|192.182.1.0|255.255.255.0|192.182.1.10|
||A13|192.182.20.0|255.255.252.0|192.182.1.10|
||FUKUROU|10.151.79.108|255.255.255.252|192.182.1.10|
|**WATER7**|DEFAULT|0.0.0.0|0.0.0.0|192.182.0.1|
||A5|192.182.24.0|255.255.248.0|192.182.0.6|
||A6|192.182.0.128|255.255.255.128|192.182.0.6|
|**PUCCI**|DEFAULT|0.0.0.0|0.0.0.0|192.182.0.5|
|**GUANHAO**|DEFAULT|0.0.0.0|0.0.0.0|192.182.0.9|
||A10|192.182.0.16|255.255.255.240|192.182.2.2|
||A12|192.182.1.0|255.255.255.0|192.182.0.14|
||A13|192.182.20.0|255.255.252.0|192.182.0.14|
||FUKUROU|10.151.79.108|255.255.255.252|192.182.0.14|
|**ALABASTA**|DEFAULT|0.0.0.0|0.0.0.0|192.182.2.1|
|**OIMO**|DEFAULT|0.0.0.0|0.0.0.0|192.182.0.13|
||A13|192.182.20.0|255.255.252.0|192.182.1.2|
|**SEASTONE**|DEFAULT|0.0.0.0|0.0.0.0|192.182.1.1|

* Konfigurasi Routing

Foosha  
```
192.182.16.0/22 via 192.182.27.150
192.182.27.0/25 via 192.182.27.150
192.182.0.0/21 via 192.182.27.150
192.182.20.0/22 via 192.182.27.154
192.182.24.0/23 via 192.182.27.154
192.182.27.128/28 via 192.182.27.154
192.182.26.0/24 via 192.182.27.154
192.182.12.0/22 via 192.182.27.154
192.182.27.164/30 via 192.182.27.154
192.182.27.156/30 via 192.182.27.154
192.182.27.144/30 via 192.182.27.150
```
Water7
```
0.0.0.0/0 via 192.182.27.149
192.182.27.0/25 via 192.182.27.146
192.182.0.0/21 via 192.182.27.146
```
Pucci
```
0.0.0.0/0 via 192.182.27.145
```
Guanhao
```
0.0.0.0/0 via 192.182.27.153
192.182.27.128/28 via 192.182.24.3
192.182.26.0/24 via 192.182.27.158
192.182.12.0/22 via 192.182.27.158
192.182.27.164/30 via 192.182.27.158
```
Oimo
```
0.0.0.0/0 via 192.182.27.157
192.182.12.0/22 via 192.182.26.3
```
Alabasta
```
0.0.0.0/0 via 192.182.24.1
```
Seastone
```
0.0.0.0/0 via 192.182.26.1
```


## GNS3 - CIDR
### Pembagian subnet
**Langkah 1**
![c1](https://user-images.githubusercontent.com/31863229/142777462-03a67e5a-f0e3-4b3a-9223-b0ea659e6fc0.png)

**Langkah 2**
![g1](https://user-images.githubusercontent.com/31863229/142810611-684a1bbe-ae73-4aab-b6af-066ca8f4b5de.png)

**Langkah 3**
![g2](https://user-images.githubusercontent.com/31863229/142810624-4624bd3d-4aba-46d8-8ff6-791b7d7b6ac9.png)

**Langkah 4**
![g3](https://user-images.githubusercontent.com/31863229/142810638-386b21d0-db72-4910-9c44-83e4bb77d5d4.png)

**Langkah 5**
![g4](https://user-images.githubusercontent.com/31863229/142810659-a6eb3d31-9f39-4485-a887-528b4991a923.png)

**Langkah 6**
![g5](https://user-images.githubusercontent.com/31863229/142810676-1511d433-8618-47a0-8455-ca97d4463541.png)

**Langkah 7**
![g6](https://user-images.githubusercontent.com/31863229/142810689-9edecc00-5d43-432a-84fd-f54066365f68.png)

**Hasil subnetting**
![g7](https://user-images.githubusercontent.com/31863229/142810707-01d3c9a7-7030-45a5-9849-fc243a400e2b.png)

### CIDR Tree
![g8](https://user-images.githubusercontent.com/31863229/143030104-10faa525-ee24-4d32-aaaa-b598e6233d9e.png)

* Konfigurasi GNS3  

Foosha
```
route add -net 192.182.128.0 netmask 255.255.128.0 gw  192.182.192.2
route add -net 192.182.0.0 netmask 255.255.128.0 gw 192.182.32.2
```
Guanhao
```
route add -net 192.182.0.0 netmask 255.255.240.0 gw 192.182.8.2
route add -net 192.182.16.0 netmask 255.255.248.0 gw 192.182.16.3
```
Oimo
```
route add -net 192.182.0.0 netmask 255.255.252.0 gw 192.182.4.3
```
Water7
```
route add -net 192.182.128.0 netmask 255.255.192.0 gw 192.182.144.2
```
Pada router FOOSHA, jalankan:
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.182.0.0/16
```

Pada semua node (router dan client) selain FOOSHA, jalankan:
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
```

## Kendala
1. Sedikit bingung dengan pembagian subnet dan pembuatan pohon VLSM dan CIDR.
2. Sedikit bingung dengan routing.
