### QtGlobal

Заголовочный файл `<QtGlobal>` содержит следующие полезные типы: `QFunctionPointer`, `QtMessageHandler`, `QtMsgType`, `qint8`, `qint16`, `qint32`, `qint64`, `qintptr`, `qlonglong`, `qptrdiff`, `qreal`, `qsizetype`, `quint8`, `quint16`, `quint32`, `quint64`, `quintptr`, `qulonglong`, `uchar`, `uint`, `ulong`, `ushort`.

#### Функции

```
T	qAbs(const T &t);
typename std::add_const<T>::type &	qAsConst(T &t);
void	qAsConst(const T &&t);
const T &	qBound(const T &min, const T &val, const T &max);
auto	qConstOverload(T memberFunctionPointer);
QString	qEnvironmentVariable(const char *varName);
QString	qEnvironmentVariable(const char *varName, const QString &defaultValue);
int	qEnvironmentVariableIntValue(const char *varName, bool *ok = nullptr);
bool	qEnvironmentVariableIsEmpty(const char *varName);
bool	qEnvironmentVariableIsSet(const char *varName);
quint32	qFloatDistance(float a, float b);
quint64	qFloatDistance(double a, double b);
QString	qFormatLogMessage(QtMsgType type, const QMessageLogContext &context, const QString &str);
bool	qFuzzyCompare(double p1, double p2);
bool	qFuzzyCompare(float p1, float p2);
bool	qFuzzyIsNull(double d);
bool	qFuzzyIsNull(float f);
double	qInf();
QtMessageHandler	qInstallMessageHandler(QtMessageHandler handler);
bool	qIsFinite(double d);
bool	qIsFinite(float f);
bool	qIsInf(double d);
bool	qIsInf(float f);
bool	qIsNaN(double d);
bool	qIsNaN(float f);
const T &	qMax(const T &a, const T &b);
const T &	qMin(const T &a, const T &b);
auto	qNonConstOverload(T memberFunctionPointer);
auto	qOverload(T functionPointer);
double	qQNaN();
qint64	qRound64(double d);
qint64	qRound64(float d);
int	qRound(double d);
int	qRound(float d);
double	qSNaN();
void	qSetMessagePattern(const QString &pattern);
const char *	qVersion();
T *	q_check_ptr(T *p);
QByteArray	qgetenv(const char *varName);
bool	qputenv(const char *varName, const QByteArray &value);
QString	qtTrId(const char *id, int n = ...);
bool	qunsetenv(const char *varName);
```

и много макросов, из которых для нас наибольший интерес представляют

```
QT_POINTER_SIZE
QT_VERSION
QT_VERSION_STR
void	Q_ASSERT(bool test)
void	Q_ASSERT_X(bool test, const char *where, const char *what)
void	Q_ASSUME(bool expr)
Q_FOREACH(variable, container)
Q_FOREVER
Q_OS_WIN32
Q_OS_WIN64
Q_OS_WIN
Q_PROCESSOR_X86
Q_PROCESSOR_X86_32
Q_PROCESSOR_X86_64
oid	Q_UNREACHABLE
Q_UNUSED(name)
foreach(variable, container)
forever
qCritical(const char *message, ...)
qDebug(const char *message, ...)
qFatal(const char *message, ...)
qInfo(const char *message, ...)
qMove(x)
const char *	qPrintable(const QString &str)
const wchar_t *	qUtf16Printable(const QString &str)
const char *	qUtf8Printable(const QString &str)
qWarning(const char *message, ...)
```