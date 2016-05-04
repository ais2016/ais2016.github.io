---
layout: post
title: Кросс-платформенная разработка
---

# Кросс-платформенная разработка

## GTK

Написана на Си.

```
#include <gtk/gtk.h>

int main(int argc, char** argv)
{
	GtkWidget *window;
	GtkWidget *btn;
	gtk_init(&argc, &argv);
	window = gtk_window_new(GTK_WINDOW_TOPLEVEL);
	btn = gtk_button_new_with_label("Hello, world!");
	gtk_container_add(GTK_CONTAINER(window), btn);
	gtk_widget_show(window);
	gtk_widget_show(btn);
	gtk_main();
	exit(0);
}
```

```
gcc -g `pkg-config --cflags gtk+-2.0` `pkg-config --libs gtk+-2.0`  gtk.c
```

## Qt

```
#include <Qt/qapplication.h>
#include <Qt/qpushbutton.h>

int main(int argc, char** argv)
{
	QApplication app(argc, argv);
	QPushButton btn("Hello, world!", 0);
	btn.resize(100, 20);
	btn.show();
	return app.exec();
}
```

```
qmake -project
qmake
make
```

Qt Creator

## Mono

Клон .NET, созданный Мигелем де Иказой в 2001.
Версия 1.0 вышла в 2004.

apt-get install mono  
monodevelop  
mdb - отладчик  

Использует GTK для отображения форм. System.Windows.Forms поддержан ограниченно.

Имеется клон silverlight - moonlight

```
gmcs -out:file.exe -target:exe -recurse:*.cs
```

# Практика

1. Написать просмотрщик (без редактирования!) текстовых файлов на qt при помощи qtcreator (должны быть меню Файл-Открыть, Файл-Выход, Справка - О программе с окошком "О программе"). Размер текстового поля должен всегда соответствовать размеру окна.







