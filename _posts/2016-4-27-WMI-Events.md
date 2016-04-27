---
layout: post
title: WMI: события
---

# WMI: события

## WQL

На WMI-хранилище можно смотреть как на базу
данных.

WQL - WMI Query Language
SELECT * From Win32_Process

SELECT * From Win32_Service Where Name='W32Time'

```
objWMIService = GetObject("winmgmts:\\\\.\\root\\CIMV2");
var colItems = objWMIService.ExecQuery(
	"SELECT * FROM Win32_Service " +
	"where Name = 'W32Time' or Name = 'SkypeUpdate'");
var e = new Enumerator(colItems);
for(;!e.atEnd();e.moveNext()) {
    WScript.Echo(e.item().Name);
}
```

## События
События создания объекта, изменения объекта и 
удаления объекта.

```
wmi = GetObject("winmgmts:\\\\.\\root\\CIMV2");
serviceMonitor = wmi.ExecNotificationQuery(
	"SELECT * FROM __InstanceModificationEvent " +
 	"WITHIN 1 WHERE TargetInstance ISA 'Win32_Service'");
WScript.Echo("Waiting for service to start/stop ...");
while (1) {
  latestEvent = serviceMonitor.NextEvent();
  instance = latestEvent.TargetInstance;
  WScript.Echo ("Service Name: " + instance.Name );
}
```
__InstanceCreationEvent - событие на создание объекта  
__InstanceModificationEvent - событие на изменение объекта  
__InstanceDeletionEvent - событие на удаление объекта

## Практика
1. Скрипт, который не даёт запустить блокнот (через события).  
2. Отслеживание подключения USB-storage устройств,
  вывод в консоль имени подключенного диска (Win32_LogicalDisk).
