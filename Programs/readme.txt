Tex.Asm/Programs
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

16_1.asm - заменяет обработчик 16 прерывания на свой, который просто ловит 16 прерывание и передает его дальше (через far jmp). Еще просто так печатает Hello KBD (это, видимо, для того, чтобы мы знали, что если напечаталось, то теперь наш обработчик сидит в резидентах)

16_2.asm -  В ней мы делаем свой обработчик 16 int, в котором вызываем исходный обработчик через call far и после этого возвращаем управление (при этом можем еще что-нибудь сделать до или после вызова исходного обработчика).

Разговор о 16_2.txt - объяснение смысла 11-25 строчек.

16_2C.asm - программа из разговора о 16_2.asm. Проверку осуществляем так: Вначале запускаем 16_2С, когда 16_2 не лежит в резидентах. Видим, что нажимая любую клавишу значение IF не меняется. А потом запускаем в резиденты 16_2 и запускаем 16_2С. Видим, что после первого нажатия на любую клавишу IF стал нулем, причем на следующих нажатиях он так и остается нулем. Но если нажмем Esc, то выйдем все равно из программы, то есть в принципе ничего не умерло.

16_3.asm - Ставим свой обработчик 16 прерывания, но не передаем в нем управление дальше, а просто возвращаем управление. Можно увидеть, что так все будет плохо.

9.asm - просто ставим свой обработчик 9 инта (через сервисы ДОСа), который внутри себя передает управление оригинальному обработчику.

9_1.asm - тоже самое, что и 9.asm, но теперь мы перед вызовом оригинального обработчика еще и печатаем скан код (печатаем через сервисы ДОСа)

9_2.asm - тоже самое, что и 9_1.asm, но теперь печать скан кода происходит через 10 прерывание (через биос)

9_3.asm - тоже самое, что и 9_2.asm, но теперь мы не передаем управление оригинальному обработчику, а просто делаем iret (при этом не забыли отправить End-of-Interrupt signal), так что все продолжает работает, а не умирает.

Разговор о 9-х программах.txt - обсуждается причина появления символов после конца работы программ.

10.asm - программа демонстрирующая реализацию задержки на основе цикла по таймеру.

Разговор о 10.txt - обсуждаются неясные моменты 10.asm

DM.com - программа для просмотра памяти (в верхнем правом углу появляется содержимое памяти)

PN.com - программа для работы со страницами. (то есть для переключения страниц экрана)

V1.com - программа, пытающаяся вывести текст напрямую в видеопамять. Проблема в том, что мы забыли, что у каждого символа там есть атрибуты, поэтому некоторые символы распознались как атрибуты, а не как символы

V2.com - тоже самое, что и V1, но теперь мы записываем атрибуты и текст выводится нормально.

V3.com - тоже самое, что и V2, но теперь мы печатаем на первой странице, а не на нулевой. 

Дабы кириллица корректно отображалась в DOS, надо сменить кодировку на CP866
