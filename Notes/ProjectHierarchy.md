### Иерархия проектов в Qt Creator

Сложную разветвленную иерархию проектов в Qt Creator можно организовать при помощи специального проекта "Subdirs". В данном примере я покажу, как создать проект из трёх подпроектов: DLL-библиотеки, тестов и консольного приложения, использующего DLL.

![QtProj01](img/QtProj01.png)

![QtProj02](img/QtProj02.png)

![QtProj03](img/QtProj03.png)

Добавляем субпроект типа "Библиотека":

![QtProj04](img/QtProj04.png)

![QtProj05](img/QtProj05.png)

Реализуем простейшую библиотеку из одного класса с двумя статическими методами:

```cpp
// mylibrary.h
#ifndef MYLIBRARY_H
#define MYLIBRARY_H

#include "mylibrary_global.h"

class MYLIBRARYSHARED_EXPORT MyLibrary
{
public:
    static int addition(int first, int second);
    static int substraction(int first, int second);
};

#endif // MYLIBRARY_H
```

```cpp
// mylibrary.cpp
#include "mylibrary.h"

int MyLibrary::addition(int first, int second) {
    return first + second;
}

int MyLibrary::substraction(int first, int second) {
    return first - second;
}
```

Теперь можно добавить приложение, использующее эту библиотеку:

![QtProj06](img/QtProj06.png)

![QtProj07](img/QtProj07.png)

В приложение добавляем ссылку на только что созданную библиотеку:

![QtProj08](img/QtProj08.png)

![QtProj09](img/QtProj09.png)

![QtProj10](img/QtProj10.png)

Добавляем в приложение код, использующий библиотеку:

```cpp
#include <QtCore>

#include "mylibrary.h"

int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);

    qDebug() << MyLibrary::addition(1, 2);
    qDebug() << MyLibrary::substraction(1, 2);

    return a.exec();
}
```

Собираем проект. Чтобы запустить приложение, вручную копируем DLL в папку с EXE-файлом. Возможно, существует способ автоматизировать это копирование, но я его не нашёл.

![QtProj11](img/QtProj11.png)

Теперь добавляем отдельный проект для тестов. В нем также создаём ссылку на MyLibrary (точно также как и в EXE-файл).

![QtProj12](img/QtProj12.png)

![QtProj13](img/QtProj13.png)

![QtProj14](img/QtProj14.png)

![QtProj15](img/QtProj15.png)

Код тестового проекта:

```cpp
#include <QtCore>
#include <QtTest>

#include "mylibrary.h"

class FirstTest : public QObject
{
    Q_OBJECT

public:
    FirstTest();
    ~FirstTest();

private slots:
    void test_case1();
};

FirstTest::FirstTest() {
}

FirstTest::~FirstTest() {
}

void FirstTest::test_case1() {
    QVERIFY(MyLibrary::addition(1, 2) == 3);
    QVERIFY(MyLibrary::substraction(1, 2) == -1);
}

QTEST_APPLESS_MAIN(FirstTest)

#include "tst_firsttest.moc"
```

Собираем проект (не забываем скопировать вручную DLL в папку с EXE-файлом), запускаем тесты с помощью специального пункта меню:

![QtProj16](img/QtProj16.png)

Ура! Все тесты зеленые!

![QtProj17](img/QtProj17.png)

Итого: у нас есть "сводный" проект, который включает в себя три подпроекта: DLL-библиотеку, консольное приложение и набор тестов. Собрать такой проект можно как с помощью Qt Creator, так и с помощью командной строки (не забыть скопировать MyLibrary.dll!):

```
qtvars.cmd
qmake
nmake
copy MyLibrary\release\MyLibrary.dll MyApplication\release\
copy MyLibrary\release\MyLibrary.dll MyTests\release\
```

![QtProj18](img/QtProj18.png)

Как выглядит "главный" pro-файл:

```
TEMPLATE = subdirs

SUBDIRS += \
    MyLibrary \
    MyApplication \
    MyTests
```

Как выглядит pro-файл консольного приложения:

```
QT -= gui

CONFIG += c++11 console
CONFIG -= app_bundle

SOURCES += \
        main.cpp

qnx: target.path = /tmp/$${TARGET}/bin
else: unix:!android: target.path = /opt/$${TARGET}/bin
!isEmpty(target.path): INSTALLS += target

INCLUDEPATH += $$PWD/../MyLibrary
DEPENDPATH += $$PWD/../MyLibrary

win32:CONFIG(release, debug|release): LIBS += -L$$OUT_PWD/../MyLibrary/release/ -lMyLibrary
else:win32:CONFIG(debug, debug|release): LIBS += -L$$OUT_PWD/../MyLibrary/debug/ -lMyLibrary
```

Как выглядит pro-файл тестов:

```
QT += testlib
QT -= gui

CONFIG += qt console warn_on depend_includepath testcase
CONFIG -= app_bundle

TEMPLATE = app

SOURCES +=  tst_firsttest.cpp

win32:CONFIG(release, debug|release): LIBS += -L$$OUT_PWD/../MyLibrary/release/ -lMyLibrary
else:win32:CONFIG(debug, debug|release): LIBS += -L$$OUT_PWD/../MyLibrary/debug/ -lMyLibrary

INCLUDEPATH += $$PWD/../MyLibrary
DEPENDPATH += $$PWD/../MyLibrary
```
