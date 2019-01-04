### Hello World

Создаем где-нибудь на путях файл `qtvars.cmd` следующего содержания:

```
@echo off

set QTDIR=C:\Qt\5.10.1\msvc2017_64
set PATH=%QTDIR%\bin;%PATH%
call "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"
```

Последующие действия выполняем в `cmd.exe`, предварительно запустив `qtvars.cmd`.

Создаём папку `hello` (так удобнее), в ней файл `hello.pro` следующего содержания:

```
CONFIG += console

SOURCES = hello.cpp
```

и файл `hello.cpp`:

```c++
#include <QCoreApplication>
#include <QDebug>

int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);

    qDebug() << "Hello, World!";

    return a.exec();
}
```

Теперь подаем команды

```
qmake
nmake
```

Если всё прошло нормально, в папке `release` появятся два файла: `hello.obj` и `hello.exe`. Созданное приложение можно выполнить прямо в текущей сессии:

```
release\hello
```

(завершение приложения -- `Ctrl+C`), для эксплуатации приложения на других системах его рекомендуется дополнить библиотеками Qt:

```
windeployqt -no-translations -no-compiler-runtime release\hello.exe

```

Ключи `-no-translations` и `-no-compiler-runtime` указываются по ситуации.
