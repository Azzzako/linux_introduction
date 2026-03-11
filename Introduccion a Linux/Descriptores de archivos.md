Un descriptor de archivo es un numero que usa Bash para saber donde leer y donde escribir.
Cuando un programa se encuentra en ejecución el stdout no se manda directamente a un archivo o a "la pantalla" directamente, sino que el sistema dice:

0 = entrada
1 = salida
2 = errores
3, 4, 5... = descriptores creados por el usuario

En el siguiente ejemplo

```
exec 3<> file
```

Se crea un descriptor con numero 3 que esta conectado a file.
El simbolo < funciona para crearlo con capacidad de lectura
el simbolo > lo crea con capacidad de escritura

Como si quisieramos mandar el error al "agujero negro", podemos mandar la salida al descriptor 3 de las siguientes maneras

```
> whoami >&3
> pwd >&3
```

Es como decir "Manda este mensaje al descriptor con numero 3"

-----

Para cerrar el descriptor de archivo podemos usar el siguiente comando 
```
exec 3>&-
```

Esto no significa que el archivo haya perdido su contenido, sino que dejamos libre el descriptor numero 3 y lo que hemos almacenado en file esta intacto.

Si intentamos almacenar algo en el descriptor 3 despues de haberlo cerrado la consola nos arrojara un error: 

```
> zsh 3: bad file descriptor
```

