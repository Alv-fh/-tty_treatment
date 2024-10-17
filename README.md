## Como hacer un tratamiento de la TTY paso a paso ✅

#### > Teniendo en cuenta que hemos conseguido una Reverse-Shell y que hemos llegado a este punto hacemos lo siguiente.

![image](https://github.com/user-attachments/assets/8075b3ba-0ed1-466c-b291-0673e35568a0)

## Paso 1 

`script /dev/null -c bash`

Escribimos el siguiente comando para iniciar una grabación de la sesión de terminal. En este caso, se está utilizando de una manera ligeramente distinta para reconfigurar el entorno terminal, ejecutando un nuevo shell de Bash.


![image](https://github.com/user-attachments/assets/ef5ce946-81dc-4fcf-9f5c-f27e4158bd57)

## Paso 2 

`Ctrl + Z`

Lo que hace la combinación de teclas `Ctrl + Z` es suspender el proceso actual y devolver el control al shell que lo invocó. Esto permite que el proceso de bash continúe en segundo plano para realizar ajustes en la terminal.

![image](https://github.com/user-attachments/assets/d4b88316-8817-4a0f-8deb-83b3a04138f7)

## Paso 3

`stty raw -echo; fg`

Este es un comando compuesto que realiza dos tareas:

`raw`: Configura el terminal en "modo raw", donde el sistema no interpreta los caracteres de control (como Ctrl+C o Ctrl+Z), enviando todo tal como se introduce.

`-echo`: Desactiva el "eco" de la terminal, es decir, lo que escribes en la terminal no aparecerá en pantalla (útil para que las contraseñas o comandos no sean visibles).
Esto puede ser útil para trabajar en una terminal desconfigurada o con mal comportamiento.

`fg`: El comando fg trae de vuelta al primer plano el proceso que se había suspendido (en este caso, el bash que suspendiste con Ctrl+Z).

Este paso cambia el comportamiento de la terminal y luego reanuda el shell suspendido.

![image](https://github.com/user-attachments/assets/7dab5d24-37e3-4d53-95e8-1503ed20fa4b)


## Paso 4

`reset xterm`

El comando `reset` se utiliza para restaurar la configuración de la terminal a su estado predeterminado. La opción `xterm` le dice específicamente que quieres restablecer la terminal como si fuera una terminal de tipo xterm (un emulador de terminal común en Linux).

![image](https://github.com/user-attachments/assets/ee8d36c0-8077-42a9-bad2-92912d2537f0)

## Paso 5

`export SHELL=bash`

El comando `export` se utiliza para definir variables de entorno. En este caso, se establece que el shell actual que se utiliza es bash.

![image](https://github.com/user-attachments/assets/8d7759ff-ddc2-46f1-b844-f010a9667daa)

## Paso 6

`export TERM=xterm`

Este comando exporta la variable de entorno TERM, que le indica a las aplicaciones que se ejecutan en la terminal qué tipo de terminal están utilizando. El valor xterm es uno de los tipos de terminal más comunes y utilizados en sistemas Linux y Unix.

![image](https://github.com/user-attachments/assets/c2da5a3c-f1f3-4ab5-acdd-7380fd165ad0)

## Paso 7

`stty rows NUM columns NUM`

Ahora tenemos que ajustar la proporción de la pantalla ya que "casi" siempre viene en una mala proporción y es necesario para que no ocurran este tipo de cosas.

![image](https://github.com/user-attachments/assets/15ef43e1-f6d3-4894-9741-32982079d343)

Entonces primero debemos de mirar en una nueva consola la proporción de nuestro Kali Linux por ejemplo.

`stty -a`

![image](https://github.com/user-attachments/assets/79279988-5b94-4a37-8409-b6ab2c3144d1)

Rows -> 40

Columns -> 189

Volvemos a la Reverse Shell y escribimos el siguiente comando para ajustar la proporción de la pantalla.

`stty rows 40 columns 189`

![image](https://github.com/user-attachments/assets/f0add440-6b8a-4ad7-8070-37351dad47aa)

Ya hemos hecho un tratamiento de la TTY correctamente :)

Vemos que ya si podemos poner todo el comando sin que salte a la siguiente linea.

![image](https://github.com/user-attachments/assets/6be742dc-0ca1-44f1-8b9b-491047a32435)



