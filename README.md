Tex.Asm
=======
1.asm - выводит сообщение на экран

2.asm - выводит сообщение на экран и остается в памяти после завершения (резидент)

3.asm - пример "пристановки работы программы", по факту просто вызываем функцию чтения с клавиатуры, что заставляет нас ждать ввода. И, пока мы что-нибудь не введем, программа не продолжит работать.

4.asm - пример для показа работы hlt (инструкция специально сделанная для приостановки)

5.asm - программа печатающая сегмент в памяти, куда она загрузилась

6.asm - программа показывающая как заменять стандартный обработчик конкретного прерывания на свой.

7.asm - делает тоже самое, что и 6.asm, но делает так, как это было у Gary Kildall (читаем третью лекцию)

8r.asm - тоже самое, что и 7.asm, но ко всему прочему оставляет наш обработчик в памяти, то есть если мы после выполнения 8r вызовем прерывание 0F1h, то вызовется наш обработчик

8с.asm - вызываем после выполнения 8r и видим, что наш обработчик действительно остался в памяти и вызывается именн он.

DEB_1.asm - программа, которая загружает в свое адресное пространство другую программу

HW1.asm - программа, которую загружает DEB_1.asm

В папке Debugger рабочий отладчик для первого домашнего задания

Дабы кириллица корректно отображалась в DOS, надо сменить кодировку на CP866

Лекции в папке text
