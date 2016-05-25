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
		<style>
			th, td { 
				padding: 2px 10px 2px 10px;
			}
		
			table, td, tr, th { 
				border: solid 1px black; 
				border-collapse: collapse;
			}
		</style>
	</head>
	<body>
		<script>
			function a()
			{
				var table = document.getElementById("processTable");
				for (var i = 0; i < 5; i++)
				{
					var child = document.createElement("tr");
					var td1 = document.createElement("td");
					var td2 = document.createElement("td");
					var td3 = document.createElement("td");
					var btn = document.createElement("input");
					
					td1.innerHTML = "abc";
					td2.innerHTML = "cde";
					td2.innerHTML = "def";
					
					btn.type = "button";
					btn.value = "Kill!";
					btn.onclick = function() { alert("Hello, world"); };
					
					child.appendChild(td1);
					child.appendChild(td2);
					child.appendChild(td3);
					td3.appendChild(btn);
					table.appendChild(child);
				}
			}
		</script>
		<table cellspacing="0" cellpadding="0">
			<thead>
				<tr>
					<th>PID</th>
					<th>Title</th>
					<th>&nbsp;</th>
				</tr>
			</thead>
			<tbody id="processTable">
			</tbody>
		</table>

	</body>
</html>
```

Практика.  
1. Просмотрщик списка запущенных процессов с возможностью их закрытия (HTA, WMI)
