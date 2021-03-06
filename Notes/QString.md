### QString

#### Public types

```
class	Null
typedef	ConstIterator
typedef	Iterator
enum	NormalizationForm { NormalizationForm_D, NormalizationForm_C, NormalizationForm_KD, NormalizationForm_KC }
enum	SectionFlag { SectionDefault, SectionSkipEmpty, SectionIncludeLeadingSep, SectionIncludeTrailingSep, SectionCaseInsensitiveSeps }
flags	SectionFlags
enum	SplitBehavior { KeepEmptyParts, SkipEmptyParts }
typedef	const_iterator
typedef	const_pointer
typedef	const_reference
typedef	const_reverse_iterator
typedef	difference_type
typedef	iterator
typedef	pointer
typedef	reference
typedef	reverse_iterator
typedef	size_type
typedef	value_type
```

#### Public functions

```
QString()
QString(const QChar *unicode, int size = -1)
QString(QChar ch)
QString(int size, QChar ch)
QString(QLatin1String str)
QString(const QString &other)
QString(QString &&other)
QString(const char *str)
QString(const QByteArray &ba)
~QString()
QString &	append(const QString &str)
QString &	append(const QChar *str, int len)
QString &	append(QChar ch)
QString &	append(const QStringRef &reference)
QString &	append(QLatin1String str)
QString &	append(const char *str)
QString &	append(const QByteArray &ba)
QString	arg(const QString &a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' ')) const
QString	arg(qulonglong a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(long a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(ulong a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(uint a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(short a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(ushort a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(double a, int fieldWidth = 0, char format = 'g', int precision = -1, QChar fillChar = QLatin1Char(' ')) const
QString	arg(char a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' ')) const
QString	arg(QChar a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' ')) const
QString	arg(qlonglong a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' ')) const
QString	arg(QStringView a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' ')) const
QString	arg(QLatin1String a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' ')) const
QString	arg(const QString &a1, const QString &a2) const
QString	arg(const QString &a1, const QString &a2, const QString &a3) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4, const QString &a5) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4, const QString &a5, const QString &a6) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4, const QString &a5, const QString &a6, const QString &a7) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4, const QString &a5, const QString &a6, const QString &a7, const QString &a8) const
QString	arg(const QString &a1, const QString &a2, const QString &a3, const QString &a4, const QString &a5, const QString &a6, const QString &a7, const QString &a8, const QString &a9) const
const QChar	at(int position) const
QChar	back() const
QCharRef	back()
QString::iterator	begin()
QString::const_iterator	begin() const
int	capacity() const
QString::const_iterator	cbegin() const
QString::const_iterator	cend() const
void	chop(int n)
QString	chopped(int len) const
void	clear()
int	compare(const QStringRef &ref, Qt::CaseSensitivity cs = ...) const
int	compare(QLatin1String other, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	compare(QStringView s, Qt::CaseSensitivity cs = ...) const
int	compare(const QString &other, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QString::const_iterator	constBegin() const
const QChar *	constData() const
QString::const_iterator	constEnd() const
bool	contains(const QString &str, Qt::CaseSensitivity cs = ...) const
bool	contains(QChar ch, Qt::CaseSensitivity cs = ...) const
bool	contains(QLatin1String str, Qt::CaseSensitivity cs = ...) const
bool	contains(const QStringRef &str, Qt::CaseSensitivity cs = ...) const
bool	contains(const QRegExp &rx) const
bool	contains(QRegExp &rx) const
bool	contains(const QRegularExpression &re) const
bool	contains(const QRegularExpression &re, QRegularExpressionMatch *match) const
int	count(const QString &str, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	count(QChar ch, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	count() const
int	count(const QStringRef &str, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	count(const QRegExp &rx) const
int	count(const QRegularExpression &re) const
QString::const_reverse_iterator	crbegin() const
QString::const_reverse_iterator	crend() const
QChar *	data()
const QChar *	data() const
QString::iterator	end()
QString::const_iterator	end() const
bool	endsWith(const QString &s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	endsWith(const QStringRef &s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	endsWith(QStringView str, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	endsWith(QLatin1String s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	endsWith(QChar c, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QString &	fill(QChar ch, int size = -1)
QChar	front() const
QCharRef	front()
int	indexOf(const QString &str, int from = 0, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	indexOf(QChar ch, int from = 0, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	indexOf(QLatin1String str, int from = 0, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	indexOf(const QStringRef &str, int from = 0, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	indexOf(const QRegExp &rx, int from = 0) const
int	indexOf(QRegExp &rx, int from = 0) const
int	indexOf(const QRegularExpression &re, int from = 0) const
int	indexOf(const QRegularExpression &re, int from, QRegularExpressionMatch *rmatch) const
QString &	insert(int position, const QString &str)
QString &	insert(int position, const QChar *unicode, int size)
QString &	insert(int position, QChar ch)
QString &	insert(int position, const QStringRef &str)
QString &	insert(int position, QLatin1String str)
QString &	insert(int position, const char *str)
QString &	insert(int position, const QByteArray &str)
bool	isEmpty() const
bool	isLower() const
bool	isNull() const
bool	isRightToLeft() const
bool	isUpper() const
int	lastIndexOf(const QString &str, int from = -1, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	lastIndexOf(QChar ch, int from = -1, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	lastIndexOf(QLatin1String str, int from = -1, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	lastIndexOf(const QStringRef &str, int from = -1, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
int	lastIndexOf(const QRegExp &rx, int from = -1) const
int	lastIndexOf(QRegExp &rx, int from = -1) const
int	lastIndexOf(const QRegularExpression &re, int from = -1) const
int	lastIndexOf(const QRegularExpression &re, int from, QRegularExpressionMatch *rmatch) const
QString	left(int n) const
QString	leftJustified(int width, QChar fill = QLatin1Char(' '), bool truncate = false) const
QStringRef	leftRef(int n) const
int	length() const
int	localeAwareCompare(const QString &other) const
int	localeAwareCompare(const QStringRef &other) const
QString	mid(int position, int n = -1) const
QStringRef	midRef(int position, int n = -1) const
QString	normalized(QString::NormalizationForm mode, QChar::UnicodeVersion version = QChar::Unicode_Unassigned) const
QString &	prepend(const QString &str)
QString &	prepend(const QChar *str, int len)
QString &	prepend(QChar ch)
QString &	prepend(const QStringRef &str)
QString &	prepend(QLatin1String str)
QString &	prepend(const char *str)
QString &	prepend(const QByteArray &ba)
void	push_back(const QString &other)
void	push_back(QChar ch)
void	push_front(const QString &other)
void	push_front(QChar ch)
QString::reverse_iterator	rbegin()
QString::const_reverse_iterator	rbegin() const
QString &	remove(int position, int n)
QString &	remove(QChar ch, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	remove(QLatin1String str, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	remove(const QString &str, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	remove(const QRegExp &rx)
QString &	remove(const QRegularExpression &re)
QString::reverse_iterator	rend()
QString::const_reverse_iterator	rend() const
QString	repeated(int times) const
QString &	replace(int position, int n, const QString &after)
QString &	replace(int position, int n, const QChar *unicode, int size)
QString &	replace(int position, int n, QChar after)
QString &	replace(QChar before, QChar after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(const QChar *before, int blen, const QChar *after, int alen, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(QLatin1String before, QLatin1String after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(QLatin1String before, const QString &after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(const QString &before, QLatin1String after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(const QString &before, const QString &after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(QChar ch, const QString &after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(QChar c, QLatin1String after, Qt::CaseSensitivity cs = Qt::CaseSensitive)
QString &	replace(const QRegExp &rx, const QString &after)
QString &	replace(const QRegularExpression &re, const QString &after)
void	reserve(int size)
void	resize(int size)
void	resize(int size, QChar fillChar)
QString	right(int n) const
QString	rightJustified(int width, QChar fill = QLatin1Char(' '), bool truncate = false) const
QStringRef	rightRef(int n) const
QString	section(QChar sep, int start, int end = ..., QString::SectionFlags flags = SectionDefault) const
QString	section(const QString &sep, int start, int end = -1, QString::SectionFlags flags = SectionDefault) const
QString	section(const QRegExp &reg, int start, int end = -1, QString::SectionFlags flags = SectionDefault) const
QString	section(const QRegularExpression &re, int start, int end = -1, QString::SectionFlags flags = SectionDefault) const
QString &	setNum(int n, int base = 10)
QString &	setNum(ushort n, int base = 10)
QString &	setNum(short n, int base = 10)
QString &	setNum(uint n, int base = 10)
QString &	setNum(long n, int base = 10)
QString &	setNum(ulong n, int base = 10)
QString &	setNum(qlonglong n, int base = 10)
QString &	setNum(qulonglong n, int base = 10)
QString &	setNum(float n, char format = 'g', int precision = 6)
QString &	setNum(double n, char format = 'g', int precision = 6)
QString &	setRawData(const QChar *unicode, int size)
QString &	setUnicode(const QChar *unicode, int size)
QString &	setUtf16(const ushort *unicode, int size)
void	shrink_to_fit()
QString	simplified() const
int	size() const
QStringList	split(const QString &sep, QString::SplitBehavior behavior = KeepEmptyParts, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QStringList	split(QChar sep, QString::SplitBehavior behavior = KeepEmptyParts, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QStringList	split(const QRegExp &rx, QString::SplitBehavior behavior = KeepEmptyParts) const
QStringList	split(const QRegularExpression &re, QString::SplitBehavior behavior = KeepEmptyParts) const
QVector<QStringRef>	splitRef(const QString &sep, QString::SplitBehavior behavior = KeepEmptyParts, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QVector<QStringRef>	splitRef(QChar sep, QString::SplitBehavior behavior = KeepEmptyParts, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
QVector<QStringRef>	splitRef(const QRegExp &rx, QString::SplitBehavior behavior = KeepEmptyParts) const
QVector<QStringRef>	splitRef(const QRegularExpression &re, QString::SplitBehavior behavior = KeepEmptyParts) const
void	squeeze()
bool	startsWith(const QString &s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	startsWith(const QStringRef &s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	startsWith(QStringView str, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	startsWith(QLatin1String s, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
bool	startsWith(QChar c, Qt::CaseSensitivity cs = Qt::CaseSensitive) const
void	swap(QString &other)
CFStringRef	toCFString() const
QString	toCaseFolded() const
double	toDouble(bool *ok = nullptr) const
float	toFloat(bool *ok = nullptr) const
QString	toHtmlEscaped() const
int	toInt(bool *ok = nullptr, int base = 10) const
QByteArray	toLatin1() const
QByteArray	toLocal8Bit() const
long	toLong(bool *ok = nullptr, int base = 10) const
qlonglong	toLongLong(bool *ok = nullptr, int base = 10) const
QString	toLower() const
NSString *	toNSString() const
short	toShort(bool *ok = nullptr, int base = 10) const
std::string	toStdString() const
std::u16string	toStdU16String() const
std::u32string	toStdU32String() const
std::wstring	toStdWString() const
uint	toUInt(bool *ok = nullptr, int base = 10) const
ulong	toULong(bool *ok = nullptr, int base = 10) const
qulonglong	toULongLong(bool *ok = nullptr, int base = 10) const
ushort	toUShort(bool *ok = nullptr, int base = 10) const
QVector<uint>	toUcs4() const
QString	toUpper() const
QByteArray	toUtf8() const
int	toWCharArray(wchar_t *array) const
QString	trimmed() const
void	truncate(int position)
const QChar *	unicode() const
const ushort *	utf16() const
bool	operator!=(QLatin1String other) const
bool	operator!=(const char *other) const
bool	operator!=(const QByteArray &other) const
QString &	operator+=(const QString &other)
QString &	operator+=(QChar ch)
QString &	operator+=(const QStringRef &str)
QString &	operator+=(QLatin1String str)
QString &	operator+=(const char *str)
QString &	operator+=(const QByteArray &ba)
QString &	operator+=(char ch)
bool	operator<(QLatin1String other) const
bool	operator<(const char *other) const
bool	operator<(const QByteArray &other) const
bool	operator<=(QLatin1String other) const
bool	operator<=(const char *other) const
bool	operator<=(const QByteArray &other) const
QString &	operator=(const QString &other)
QString &	operator=(QChar ch)
QString &	operator=(QLatin1String str)
QString &	operator=(QString &&other)
QString &	operator=(const char *str)
QString &	operator=(const QByteArray &ba)
QString &	operator=(char ch)
bool	operator==(QLatin1String other) const
bool	operator==(const char *other) const
bool	operator==(const QByteArray &other) const
bool	operator>(QLatin1String other) const
bool	operator>(const char *other) const
bool	operator>(const QByteArray &other) const
bool	operator>=(QLatin1String other) const
bool	operator>=(const char *other) const
bool	operator>=(const QByteArray &other) const
QCharRef	operator[](int position)
const QChar	operator[](int position) const
const QChar	operator[](uint position) const
QCharRef	operator[](uint position)
```

#### Static public members

```
QString	asprintf(const char *cformat, ...)
int	compare(const QString &s1, const QString &s2, Qt::CaseSensitivity cs = Qt::CaseSensitive)
int	compare(const QString &s1, QLatin1String s2, Qt::CaseSensitivity cs = Qt::CaseSensitive)
int	compare(QLatin1String s1, const QString &s2, Qt::CaseSensitivity cs = ...)
int	compare(const QString &s1, const QStringRef &s2, Qt::CaseSensitivity cs = ...)
QString	fromCFString(CFStringRef string)
QString	fromLatin1(const char *str, int size = -1)
QString	fromLatin1(const QByteArray &str)
QString	fromLocal8Bit(const char *str, int size = -1)
QString	fromLocal8Bit(const QByteArray &str)
QString	fromNSString(const NSString *string)
QString	fromRawData(const QChar *unicode, int size)
QString	fromStdString(const std::string &str)
QString	fromStdU16String(const std::u16string &str)
QString	fromStdU32String(const std::u32string &str)
QString	fromStdWString(const std::wstring &str)
QString	fromUcs4(const uint *unicode, int size = -1)
QString	fromUcs4(const char32_t *str, int size = -1)
QString	fromUtf8(const char *str, int size = -1)
QString	fromUtf8(const QByteArray &str)
QString	fromUtf16(const ushort *unicode, int size = -1)
QString	fromUtf16(const char16_t *str, int size = -1)
QString	fromWCharArray(const wchar_t *string, int size = -1)
int	localeAwareCompare(const QString &s1, const QString &s2)
int	localeAwareCompare(const QString &s1, const QStringRef &s2)
const QString::Null	null
QString	number(long n, int base = 10)
QString	number(uint n, int base = 10)
QString	number(int n, int base = 10)
QString	number(ulong n, int base = 10)
QString	number(qlonglong n, int base = 10)
QString	number(qulonglong n, int base = 10)
QString	number(double n, char format = 'g', int precision = 6)
QString	vasprintf(const char *cformat, va_list ap)
```

#### Related non-members

```
bool	operator!=(const QString &s1, const QString &s2)
bool	operator!=(const char *s1, const QString &s2)
const QString	operator+(const QString &s1, const QString &s2)
const QString	operator+(const QString &s1, const char *s2)
const QString	operator+(const char *s1, const QString &s2)
const QString	operator+(const QString &s, char ch)
const QString	operator+(char ch, const QString &s)
bool	operator<(const QString &s1, const QString &s2)
bool	operator<(const char *s1, const QString &s2)
QDataStream &	operator<<(QDataStream &stream, const QString &string)
bool	operator<=(const QString &s1, const QString &s2)
bool	operator<=(const char *s1, const QString &s2)
bool	operator==(const QString &s1, const QString &s2)
bool	operator==(const char *s1, const QString &s2)
bool	operator>(const QString &s1, const QString &s2)
bool	operator>(const char *s1, const QString &s2)
bool	operator>=(const QString &s1, const QString &s2)
bool	operator>=(const char *s1, const QString &s2)
QDataStream &	operator>>(QDataStream &stream, QString &string)
```

#### Macros

```
QStringLiteral(str)
QT_NO_CAST_FROM_ASCII
QT_NO_CAST_TO_ASCII
QT_RESTRICTED_CAST_FROM_ASCII
```
