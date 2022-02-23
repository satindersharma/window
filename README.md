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
