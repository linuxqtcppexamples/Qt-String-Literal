# Qt-String-Literal
Qt String Literal example

Optimizing Qt Source code with QStringLiteral

QStringLiteral is a new macro introduced in Qt 5 to create QString from string literals. (String literals are strings inside "" included in the source code).

Example:

QStringLiteralEx.pro

QT += core
QT -= gui
CONFIG += c++11
TARGET = QStringLiteralEx
CONFIG += console
CONFIG -= app_bundle
TEMPLATE = app
SOURCES += main.cpp
main.cpp

#include <QCoreApplication>
#include <QDebug>
#include <QDateTime>
void fun1(QString i_str1,QString i_str2,QString i_str3,QString i_str4)
{
    qDebug() << i_str1 << i_str2 << i_str3 << i_str4;
}
int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);
    qDebug() << QDateTime::currentDateTime().toString("yyyy-MM-dd hh:mm:ss.zzz");
    fun1("Data1","Data2","Data3","Data4");
    qDebug() << QDateTime::currentDateTime().toString("yyyy-MM-dd hh:mm:ss.zzz");
 
    qDebug() << QDateTime::currentDateTime().toString("yyyy-MM-dd hh:mm:ss.zzz");
    fun1("Data1","Data2","Data3","Data4");
    qDebug() << QDateTime::currentDateTime().toString("yyyy-MM-dd hh:mm:ss.zzz");
    return a.exec();
}
//Output:
//"2017-06-06 21:45:55.349"
//"Data1" "Data2" "Data3" "Data4"
//"2017-06-06 21:45:55.350"
//"2017-06-06 21:45:55.350"
//"Data1" "Data2" "Data3" "Data4"
//"2017-06-06 21:45:55.350"
