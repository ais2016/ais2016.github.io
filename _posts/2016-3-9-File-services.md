---
layout: post
title: Способы доступа к файлам
---

## FTP
File Transfer Protocol
21 TCP - сокет для команд

У сервера два режима - активный и пассивный
PORT и PASV 

Основные команды:  
HELP  
CWD - переход по каталогам  
LIST - список файлов в текущей директории  
RETR /имя/файла - получить содержимое файла  
STOR - сохраняет файл на сервер  

proftpd - самый популярный ftp-сервер в linux  
apt-get install proftpd

/etc/proftpd/proftpd.conf
работает только с системными пользователями
(из /etc/passwd)

Текстовый клиент для ftp - команда ftp
```
ftp localhost
```

## Samba
Linux-реализация протокола SMB  
/etc/samba/smb.conf

smbclient - консольный клиент для samba
```
smbclient -L '\\localhost'
smbclient '\\localhost\all_drive'
```

## scp
secure copy  
Копирование файлов через ssh  
ssh - Secure shell

apt-get install openssh-server  
ssh -X - проброс X-сервера  

```
scp user@192.168.5.3:/home/vasya/text.txt text.txt
scp a.out debian.org:~
```

WinSCP - клиент под винду

# Практика
1) Настроить на FTP директорию на запись, 
записать туда файл через telnet в активном 
режиме.

