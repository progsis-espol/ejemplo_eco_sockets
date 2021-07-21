# Ejemplo uso de sockets en C
Este repositorio contiene código ejemplo que demuestra el uso básico de sockets en C usando una aplicación *eco* cliente - servidor. En este ejemplo, el usuario ingresa una línea de texto desde el cliente, el cliente la envia al servidor y el servidor la envia de regreso. El código de esta aplicación está basado en el capítulo 11 de [Computer Systems: A Programmer's Perspective](http://csapp.cs.cmu.edu/3e/home.html).

## Uso
Para ejecutar el servidor se debe especificar como argumento el puerto TCP, por ejemplo:
```
./server 8080
server escuchando en puerto 8080...
```

Asumiendo que el servidor esta corriendo en una maquina con la IP 192.168.100 en el puerto 8080, ejemplo de ejecución del cliente:
```
./client 192.168.100 8080
Conectado exitosamente a 192.168.100 en el puerto 8080.
Ingrese texto para enviar al servidor, Ctrl+c para terminar...
> 
```
Si el servidor esta en la misma máquina, entonces es necesario abrir otra ventana/tab de terminal y ejecutar el cliente de esta forma:
```
$ ./client 127.0.0.1 8080
Conectado exitosamente a 127.0.0.1 en el puerto 8080.
Ingrese texto para enviar al servidor, Ctrl+c para terminar...
> 
```

## Compilación
Para compilar cliente y servidor:
```
$ make
```
Para compilar solo el servidor:
```
$ make server
```
Para compilar cliente y servidor facilitando la depuración con gdb:
```
$ make debug
```
Para compilar cliente y servidor habilitando la herramienta AddressSanitizer, facilita la depuración en tiempo de ejecución:
```
$ make sanitize
```
