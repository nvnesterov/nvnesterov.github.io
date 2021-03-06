---
title: Фильтрация записей в PowerShell
tags: powershell
---

Для того, чтобы из всех записей выбрать нужные по вложенным свойствам объекта, в powershell есть командлет Where c параметром FilterScript. Условие указывается в фигурных скобках, доступ к свойствам объекта осуществляется через $_. Например:

```powershell
Get-MyFunc | Where {($_.ExtensionData.Name -like "*tadam*")}
```

Объединяются условия с помощью логических операций:
- -and
- -or
- -xor
- -not

Операции сравнения:
- -lt - меньше, чем
- -le - меньше или равно
- -gt - больше, чем
- -ge - больше или равно
- -eq - равно
- -ne - не равно

Для сложных условий можно использовать операторы
- -like и -notlike – операторы подобия
- -contains - содержит строку
- -match - регулярные выражения
- -in - принадележит множеству


Примеры:

```powershell
Get-ChildItem | Where {($_.Name -in 'doc1.txt', 'doc2.txt')}

Get-Childitem | Where Name -match "doc.+"
```
