---
layout: post
title: WMI - Windows Management Instrumentation
---

# WMI - Windows Management Instrumentation

## Хранилище объектов.
Зарегистрированные типы классов, описывающих
структуру этих объектов - свойства, методы.

Win32_Process - текущие запущенные процессы  
Win32_Service - системные службы

wbemtest.exe - встроенная программа для исследования хранилища.
root\cimv2 - основное пространство имен.  
root\wmi- ещё одно


```javascript
objSWBEMLocator = new ActiveXObject("WbemScripting.SWbemLocator");
objService = objSWBEMLocator.ConnectServer(".","root\\CIMV2");

objSrv = objService.Get("Win32_Service.Name='SkypeUpdate'"); 
WScript.Echo(objSrv.state);
WScript.Echo(objSrv.started);
WScript.Echo(objSrv.StartMode);
objSrv.PauseService();
WScript.Sleep(2000);
WScript.Echo(objSrv.state);
```
