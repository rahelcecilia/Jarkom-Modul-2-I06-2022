# Jarkom-Modul-2-I06-2022
<strong> Our Members :
1. Muhammad Naufal Alif - 05111942000008
2. Denta Bramasta Hidayat - 5025201116
3. Rahel Cecilia Purba - 5025201155 </strong>



## 1. WISE will be used as DNS Master, Berlint as DNS Slave, and Eden will be used as Web Server. There are 2 clients, namely SSS and Garden. All nodes are connected to Ostania as the router, so they can access the internet

Ostania

```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.39.0.0/16
cat /etc/resolv.conf
```
WISE etc
```
echo "nameserver 192.168.122.1" > /etc/resolv.conf
```

**RESULT**

![](https://i.ibb.co/tctFB8x/1.jpg)

![](https://i.ibb.co/235FZqG/1-1.jpg)

![](https://i.ibb.co/1d4NNb4/1-2.jpg)

![](https://i.ibb.co/X2zbSdh/1-3.jpg)

![](https://i.ibb.co/Qf7KCTC/1-4.jpg)

![](https://i.ibb.co/xhvdR0L/1-5.jpg)

## 2. To make it easier to get information about the mission from Handler, help Loid create the main website by accessing wise.yyy.com with alias www.wise.yyy.com on the wise folder 

**WISE /etc/bind/named.conf.local**
```
zone "wise.i06.com" {
    type master;
    file "/etc/bind/wise/wise.i06.com";
};
```
**WISE /etc/bind/wise/wise.i06.com**

<img width="488" alt="image" src="https://user-images.githubusercontent.com/73649094/198837593-8d3fbb70-ddec-420e-b414-7be45f6e2090.png">

**RESULT**

![](https://i.ibb.co/6gzjWGh/2.jpg)

## 3. After that he also wants to create a subdomain eden.wise.yyy.com with alias www.eden.wise.yyy.com whose DNS is set on WISE and leads to Eden

Add eden to wise.i06.com

**WISE /etc/bind/wise/wise.i06.com**

<img width="488" alt="image" src="https://user-images.githubusercontent.com/73649094/198837724-badea52f-e1bd-4bec-8557-6ff4c404c262.png">

**RESULT**

![](https://i.ibb.co/5LgVdPD/3.jpg)

## 4. Also create a reverse domain for the main domain 

**WISE /etc/bind/named.conf.local**
```
zone "wise.i06.com" {
    type master;
    file "/etc/bind/wise/wise.i06.com";
};

zone "3.39.10.in-addr.arpa" {
    type master;
    file "/etc/bind/wise/3.39.10.in-addr.arpa";
};
```
**WISE /etc/bind/wise/3.39.10.in-addr.arpa**

<img width="482" alt="image" src="https://user-images.githubusercontent.com/73649094/198838034-050849c3-951c-49e0-a13e-d3d90cd7d758.png">

**RESULT**

![](https://i.ibb.co/9qwVdLn/4.jpg)

## 5. To stay in touch if the WISE server has some problem, make Berlint also as the DNS Slave for the main domain

**WISE /etc/bind/named.conf.local**
```
zone "wise.i06.com" {
    type master;
    file "/etc/bind/wise/wise.i06.com";
    allow-transfer { 10.39.2.2; };
    also-notify { 10.39.2.2; };
    notify yes;
};

zone "3.39.10.in-addr.arpa" {
    type master;
    file "/etc/bind/wise/3.39.10.in-addr.arpa";
};
```

**Berlint /etc/bind/named.conf.local**
```
zone "wise.i06.com" {
    type slave;
    masters { "10.39.3.2"; }; // Masukan IP EniesLobby tanpa tanda petik
    file "/var/lib/bind/wise.i06.com";
};
```
**Stop WISE service bind9**

![](https://i.ibb.co/6ZkkF8Y/5.jpg)

**RESULT**

![](https://i.ibb.co/3FfTJsG/5-1.jpg)

## 6. Because there is a lot of information from Handler, make a special subdomain for operations operation.wise.yyy.com with alias www.operation.wise.yyy.com delegated from WISE to Berlint with IP leads to Eden on the folder operation

**WISE /etc/bind/wise/wise.i06.com**

<img width="486" alt="image" src="https://user-images.githubusercontent.com/73649094/198838397-43c62441-301e-4e94-ad48-d3a6afb2c137.png">

**WISE /etc/bind/named.conf.options**

comment dnssec-validation auto and add allow-query{any;};

**Berlint /etc/bind/named.conf.options**

comment dnssec-validation auto and add allow-query{any;};

**Berlint /etc/bind/named.conf.local**
```
zone "wise.i06.com" {
    type slave;
    masters { "10.39.3.2"; }; // Masukan IP EniesLobby tanpa tanda petik
    file "/var/lib/bind/wise.i06.com";
};

zone "operation.wise.i06.com" {
    type master;
    file "/etc/bind/operation/operation.wise.i06.com"
};
```
**Berlint /etc/bind/operation/operation.wise.i06.com**

<img width="483" alt="image" src="https://user-images.githubusercontent.com/73649094/198838624-ab163911-04e3-4afb-b610-ebdfae40c2c1.png">

**RESULT**

![](https://i.ibb.co/XY3zb4h/6.jpg)

## 7. For more specific information about Operation Strix, create a subdomain via Berlint with access strix.operation.wise.yyy.com with alias www.strix.operation.wise.yyy.com that leads to Eden

**Berlint /etc/bind/operation/operation.wise.i06.com**

<img width="488" alt="image" src="https://user-images.githubusercontent.com/73649094/198838656-082e5b84-7582-491e-afde-7a7523912cdc.png">

**RESULT**

![](https://i.ibb.co/WPDg8Lc/7.jpg)



