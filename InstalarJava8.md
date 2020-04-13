# Java en Ubuntu 14.04

Como instalar la plataforma Java JDK 8 en Ubuntu 14.04.

1. Descargar la plataforma Java JDK 8 en su última versión desde el sitio oficial de Oracle [aquí](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html). En mi caso instalaré la versión jdk-8u241-linux-x64.tar.gz.
2. Crear un nueva carpeta en el directorio **/usr/lib/jvm** y extraer el archivo mediante el comando **tar**.

    ```sh
    $ sudo mkdir /usr/lib/jvm
    $ cd ~/Descargas/
    $ sudo tar -C /usr/lib/jvm -xvf jdk-8u241-linux-x64.tar.gz
    ```
3. Cambiar los permisos de usuario propiertario a root con el comando chown.
    ```sh
    $ sudo chown -R root:root /usr/lib/jvm
    ```
4. Actualizar las alternativas del sistema con la nueva versión de Java.
     ```sh
    $ sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_241/bin/java" 1
    $ java -version
    java version "1.8.0_241"
    Java(TM) SE Runtime Environment (build 1.8.0_241-b07)
    Java HotSpot(TM) 64-Bit Server VM (build 25.241-b07, mixed mode)
    ```
