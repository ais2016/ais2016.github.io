---
layout: post
title: Приложения HTML
---

```html
<html>
	<head>
		<HTA: APPLICATION id="HTA" 
			applicationName="TEST HTA"
			border="thin"
			borderStyle="normal"
			caption="yes"
			icon="С:/temp/favicon. ico"
			maximizeButton="yes"
			minimizeButton="yes"
			showInTaskbar="no"
			windowState="normal"
			innerBorder="yes"
			navigable="yes"
			scroll="auto"
			scrollFlat="yes"
			singleInstance="yes"
			sysMenu="no"
			contextMenu="yes"
			selection="yes" 
			version="1.0" />
	</head>
	<body>
		<script>
			function a()
			{
				var wshShell = new ActiveXObject("WScript.Shell");
				wshShell.Run("notepad.exe");
			}
		</script>
		<input type="button" onclick="a()" value="Press me">
	</body>
</html>
```

Практика.  
1. Просмотрщик списка запущенных процессов с возможностью их закрытия (HTA, WMI)
