# WSH - Windows Scripting Host
JScript или VBScript  
Удобный доступ к COM-объектам.

cscript.exe - интерпретатор WSH (консолььный)  
wscript.exe - оконный интерпретатор  

.js, .vbs - типы файлов WSH

## WScript - главный объект WSH  
WScript.Echo - вывод текста на экран  
WScript.StdIn/StdOut/StdErr 	.WriteLine()  
WScript.Sleep(msec); - остановка на msec миллисекунд  
WScript.Quit(errorLevel) - выход с кодом  
WScript.Arguments - аргументы командной строки  
WScript.CreateObject  

WshShell - COM-объект для общения с оболочкой  
var WshShell = WScript.CreateObject("WScript.Shell");

WshShell.RegRead/RegWrite/RegDelete - работа с
 реестром Windows  
WshShell.Run("explorer.exe"); - запуск процессов  
WshShell.AppActivate("Имя окна");  
WshShell.SendKeys("Hello, world");  

```
var WshShell = WScript.CreateObject("WScript.Shell");
WshShell.Run("notepad.exe");
WshShell.AppActivate("cmd");
WScript.Sleep(400);
WshShell.SendKeys("Hello, world");
```

## JScript
### Объявление переменных
var abc;
var a = 10;
var r = []; - массив
var b = [ 1, 2, 4 ]; - инициализированный массив
b.push(5); - добавить в массив
b[0] = 7; - присвоить элементу массива

### Функции
```
function abc(d, e, f)
{
	return e + d * f;
}

abc(1,2,"hello"); упадет
```
### Циклы
```
for (var i = 0; i < 10; i++)
{
	WScript.Echo(i);
}
```
```
var arr = [ 1, 3, 6 ];
for (var i in arr)
	WScript.Echo(arr[i]);

arr["abc"] = 12;

while (a < b)
{

}
```
## Практика
1. Написать скрипт, вычисляющий на калькуляторе
 sin(log(10 + 4 * 2 + pi)) / 50 
2. Написать скрипт, не дающий запустить блокнот.

