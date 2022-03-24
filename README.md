# window



```batch
@echo off
start /WAIT /B python -m pip install --upgrade pip wheel setuptools
start /WAIT /B pip install Django==3.2.10
start /WAIT /B python -m venv --upgrade --upgrade-deps venv
cmd /WAIT /B /k "venv\Scripts\activate.bat"
```

### Sometimes the above is not working
```batch
@echo off
start /WAIT /B python -m pip install --upgrade pip wheel setuptools
start /WAIT /B pip install Django==3.2.10 virtualenv
start /WAIT /B virtualenv venv
cmd /WAIT /B /k "venv\Scripts\activate.bat"
```


```batch
@echo off
start /WAIT /B python -m pip install --upgrade pip wheel setuptools
start /WAIT /B pip install -r requirements.txt
```

```batch
start http://127.0.0.1:8000
cmd /k "venv\Scripts\python.exe manage.py runserver"
PAUSE
````



##### `netstat -ano | findstr :8000`
##### `taskkill /PID 19368 /F`

##### `tasklist |find "19368"`

##### `netstat -ano -p tcp |find "20108"`

##### `netstat -ano | findstr "PID :8000"`


## make bat
##### `FOR /F "tokens=4 delims= " %%P IN ('netstat -a -n -o ^| findstr :8000') DO @ECHO TaskKill.exe /PID %%P`

## for cmd
##### `FOR /F "tokens=4 delims= " %P IN ('netstat -a -n -o ^| findstr :8000') DO @ECHO TaskKill.exe /PID %P`



### Change the default direcotyr opening of terminal (WSL)
###### add the following tin bashrc
cd /mnt/d/Documents/Github


### Create your bat file
```batch

@echo off
title "Automatic Sync"
cmd /k "..\venv\Scripts\python.exe ..\manage.py runserver 5656"
PAUSE

```

### Now create a vbs file via specifieng the above bat file path
```vbs
Set WshShell = CreateObject("WScript.Shell") 
WshShell.Run chr(34) & "D:\Documents\GitHub\easybio-multi\testcmd\easybio_app.bat" & Chr(34), 0
Set WshShell = Nothing
```
