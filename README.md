# Valgrind en Windows 10!

Si estás cursando Algoritmos y Estructuras de Datos II, igual que yo, tenes windows y queres correr el Valgrind. Te recomiendo leer esto.
Armo repo público de este escrito en GitHub para futuros cambios.
Por último y ahora arranco esto es una recopilación de los tutoriales que hice para instalar Bash ubuntu en windows, make, g++ y valgrind en ubuntu.
Instalar Bash
Solo es posible si tienes Windows 10 64Bits.
 Primero abrí la ventana Configuración y dirígete a Actualización y seguridad> Para programadores. Activa aquí el botón “Modo de Programador“.

Después, abrí el Panel de control, y hace clic en “Programas“, luego hace clic en “Activar o desactivar las características de Windows” en Programas y funciones. Habilita la opción “Subsistema de Windows para Linux (Beta)” en la lista que aparece y haz clic en “Aceptar“.

Después de hacerlo, se te pedirá que reinicie el equipo. Haz clic en “Reiniciar ahora” para reiniciar tu computadora y Windows 10 instalará la nueva característica.
Después de reiniciar el equipo, haz clic en el botón Inicio (o presiona la tecla Windows), escriba “bash” y presione “Enter“.


La primera vez que ejecutes el archivo bash.exe, se te pedirá que aceptes los términos de servicio. El comando descargará entonces la aplicación Bash de linux en Windows 10 desde la tienda de Windows. Se te pedirá que crees una cuenta de usuario y una contraseña para su uso en el entorno Bash.
Instalar make y g++
Una vez hecho todo lo anterior, corremos en nuestra consola de ubuntu(tecla windows y buscamos “bash” o “ubuntu”) ejecutamos
```sh
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install build-essential
```
Chequeamos que este correctamente instalado.
```sh
$ gcc -v
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=/usr/lib/gcc/x86_64-linux-gnu/5/lto-wrapper
Target: x86_64-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Ubuntu 5.4.0-6ubuntu1~16.04.4' --with-bugurl=file:///usr/share/doc/gcc-5/README.Bugs --enable-languages=c,ada,c++,java,go,d,fortran,objc,obj-c++ --prefix=/usr --program-suffix=-5 --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --with-sysroot=/ --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --with-system-zlib --disable-browser-plugin --enable-java-awt=gtk --enable-gtk-cairo --with-java-home=/usr/lib/jvm/java-1.5.0-gcj-5-amd64/jre --enable-java-home --with-jvm-root-dir=/usr/lib/jvm/java-1.5.0-gcj-5-amd64 --with-jvm-jar-dir=/usr/lib/jvm-exports/java-1.5.0-gcj-5-amd64 --with-arch-directory=amd64 --with-ecj-jar=/usr/share/java/eclipse-ecj.jar --enable-objc-gc --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
Thread model: posix
gcc version 5.4.0 20160609 (Ubuntu 5.4.0-6ubuntu1~16.04.4)
$ make -v
GNU Make 4.1
Este programa fue construido para x86_64-pc-linux-gnu
Copyright (C) 1988-2014 Free Software Foundation, Inc.
Licencia GPLv3+: GNU GPL versión 3 o posterior <http://gnu.org/licenses/gpl.html>
Este es software libre: cualquiera es libre para redistribuirlo y modificarlo.
No existe GARANTÍA ALGUNA, hasta los límites permitidos por las leyes aplicables.
```
Si esto esta bien, entonces todo lo instalado se instaló correctamente. Si no contacta un profe o usa google para que te de una ayuda instalando esto.
Instalar Valgrind
``` sh
$ sudo apt-get install valgrind
```
Chequeamos de la forma anterior que valgrind esté instalado.
Compilar y usar Valgrind
Para compilar tenemos que borrar la carpeta cmake-build-debug, luego con el bash de ubuntu tenemos que ir a la carpeta del taller y/o tp al cual le queremos correr valgrind.
Dentro de la raíz del proyecto ejecutamos make y eso tendría que hacer un build del proyecto si todo esta bien.
``` sh
$ make
Scanning dependencies of target gtest
[ 14%] Building CXX object tests/google-test/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[ 28%] Linking CXX static library libgtest.a
[ 28%] Built target gtest
Scanning dependencies of target gtest_main
[ 42%] Building CXX object tests/google-test/CMakeFiles/gtest_main.dir/src/gtest_main.cc.o
[ 57%] Linking CXX static library libgtest_main.a
[ 57%] Built target gtest_main
Scanning dependencies of target correrTests
[ 71%] Building CXX object CMakeFiles/correrTests.dir/src/algoritmos.cpp.o
[ 85%] Building CXX object CMakeFiles/correrTests.dir/tests/algo_tests.cpp.o
[100%] Linking CXX executable correrTests
[100%] Built target correrTests
$valgrind ./correrTests
```
Y si funciono todo tendría que darte la info de valgrind.
Espero que les sirva.
Referencias
Cómo instalar y usar el Bash de Linux en Windows 10
