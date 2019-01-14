### QObject

#### Properties

```
objectName : QString
```

#### Public functions

```
	QObject(QObject *parent = nullptr)
virtual	~QObject()
bool	blockSignals(bool block)
const QObjectList &	children() const
QMetaObject::Connection	connect(const QObject *sender, const char *signal, const char *method, Qt::ConnectionType type = Qt::AutoConnection) const
bool	disconnect(const char *signal = nullptr, const QObject *receiver = nullptr, const char *method = nullptr) const
bool	disconnect(const QObject *receiver, const char *method = nullptr) const
void	dumpObjectInfo() const
void	dumpObjectTree() const
QList<QByteArray>	dynamicPropertyNames() const
virtual bool	event(QEvent *e)
virtual bool	eventFilter(QObject *watched, QEvent *event)
T	findChild(const QString &name = QString(), Qt::FindChildOptions options = Qt::FindChildrenRecursively) const
QList<T>	findChildren(const QString &name = QString(), Qt::FindChildOptions options = Qt::FindChildrenRecursively) const
QList<T>	findChildren(const QRegExp &regExp, Qt::FindChildOptions options = Qt::FindChildrenRecursively) const
QList<T>	findChildren(const QRegularExpression &re, Qt::FindChildOptions options = Qt::FindChildrenRecursively) const
bool	inherits(const char *className) const
void	installEventFilter(QObject *filterObj)
bool	isWidgetType() const
bool	isWindowType() const
void	killTimer(int id)
virtual const QMetaObject *	metaObject() const
void	moveToThread(QThread *targetThread)
QString	objectName() const
QObject *	parent() const
QVariant	property(const char *name) const
void	removeEventFilter(QObject *obj)
void	setObjectName(const QString &name)
void	setParent(QObject *parent)
bool	setProperty(const char *name, const QVariant &value)
bool	signalsBlocked() const
int	startTimer(int interval, Qt::TimerType timerType = Qt::CoarseTimer)
int	startTimer(std::chrono::milliseconds time, Qt::TimerType timerType = Qt::CoarseTimer)
QThread *	thread() const
```

#### Slots

```
void	deleteLater()
```

#### Signals

```
void	destroyed(QObject *obj = nullptr)
void	objectNameChanged(const QString &objectName)
```

#### Static public members

```
QMetaObject::Connection	connect(const QObject *sender, const char *signal, const QObject *receiver, const char *method, Qt::ConnectionType type = Qt::AutoConnection)
QMetaObject::Connection	connect(const QObject *sender, const QMetaMethod &signal, const QObject *receiver, const QMetaMethod &method, Qt::ConnectionType type = Qt::AutoConnection)
QMetaObject::Connection	connect(const QObject *sender, PointerToMemberFunction signal, const QObject *receiver, PointerToMemberFunction method, Qt::ConnectionType type = Qt::AutoConnection)
QMetaObject::Connection	connect(const QObject *sender, PointerToMemberFunction signal, Functor functor)
QMetaObject::Connection	connect(const QObject *sender, PointerToMemberFunction signal, const QObject *context, Functor functor, Qt::ConnectionType type = Qt::AutoConnection)
bool	disconnect(const QObject *sender, const char *signal, const QObject *receiver, const char *method)
bool	disconnect(const QObject *sender, const QMetaMethod &signal, const QObject *receiver, const QMetaMethod &method)
bool	disconnect(const QMetaObject::Connection &connection)
bool	disconnect(const QObject *sender, PointerToMemberFunction signal, const QObject *receiver, PointerToMemberFunction method)
const QMetaObject	staticMetaObject
QString	tr(const char *sourceText, const char *disambiguation = Q_OBJECT, int n = Q_OBJECT)
```

#### Protected functions

```
virtual void	childEvent(QChildEvent *event)
virtual void	connectNotify(const QMetaMethod &signal)
virtual void	customEvent(QEvent *event)
virtual void	disconnectNotify(const QMetaMethod &signal)
bool	isSignalConnected(const QMetaMethod &signal) const
int	receivers(const char *signal) const
QObject *	sender() const
int	senderSignalIndex() const
virtual void	timerEvent(QTimerEvent *event)
```

#### Protected variables

```
QScopedPointer<QObjectData>	d_ptr
```

