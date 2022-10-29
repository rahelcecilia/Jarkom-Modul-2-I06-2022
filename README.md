# Jarkom-Modul-2-I06-2022
<strong> Our Members :
1. Muhammad Naufal Alif - 05111942000008
2. Denta Bramasta Hidayat - 5025201116
3. Rahel Cecilia Purba - 5025201155 </strong>



## 1. To make it easier to get information about the mission from Handler, help Loid create the main website by accessing wise.yyy.com with alias www.wise.yyy.com on the wise folder.

![](https://i.ibb.co/tctFB8x/1.jpg)

![](https://i.ibb.co/235FZqG/1-1.jpg)

![](https://i.ibb.co/1d4NNb4/1-2.jpg)

![](https://i.ibb.co/X2zbSdh/1-3.jpg)

![](https://i.ibb.co/Qf7KCTC/1-4.jpg)

![](https://i.ibb.co/xhvdR0L/1-5.jpg)

## 2. After that he also wants to create a subdomain eden.wise.yyy.com with alias www.eden.wise.yyy.com whose DNS is set on WISE and leads to Eden 

![](https://i.ibb.co/6gzjWGh/2.jpg)

## 3. Also create a reverse domain for the main domain 

![](https://i.ibb.co/5LgVdPD/3.jpg)

## 4. To stay in touch if the WISE server has some problem, make Berlint also as the DNS Slave for the main domain 

![](https://i.ibb.co/5LgVdPD/3.jpg)

## 5. Because there is a lot of information from Handler, make a special subdomain for operations operation.wise.yyy.com with alias www.operation.wise.yyy.com delegated from WISE to Berlint with IP leads to Eden on the folder operation 

## 6. For more specific information about Operation Strix, create a subdomain via Berlint with access strix.operation.wise.yyy.com with alias www.strix.operation.wise.yyy.com that leads to Eden 

## 7. After configuring the server, then we need to configure the Web Server. First, with www.wise.yyy.com web server. Firstly, Loid needs a web server with DocumentRoot at /var/www/wise.yyy.com 

## 8. After that, Loid also needs that url www.wise.yyy.com/index.php/home can be www.wise.yyy.com/home 

## 9. Next, on www.eden.wise.yyy.com subdomain, Loid needs an asset storage with DocumentRoot at /var/www/eden.wise.yyy.com 

## 10. However, on /public folder, Loid just wants to do directory listing 

## 11. Not only that, Loid also wants to prepare an error 404.html file on /error folder to replace the error code on apache 

## 12. Loud also asks Franky to make a virtual host configuration for him. This virtual host aims to be able to access asset files www.eden.wise.yyy.com/public/js into www.eden.wise.yyy.com/js 

## 13. Lois asks that www.strix.operation.wise.yyy.com can only be accessed through port 15000 and port 15500 

## 14. with username authentication Twilight and password opStrix and file at /var/www/strix.operation.wise.yyy 

## 15. and everytime IP Eden accessed it will automatically redirect to www.wise.yyy.com 

## 16. Because www.eden.wise.yyy.com website have more visitors and a lot of modifications so there are more random pictures, Loid wants to change the image request that has a substring “eden” will be directed to eden.png.

## 17.  Help Agent Twilight and WISE Organization to keep the peace! 

