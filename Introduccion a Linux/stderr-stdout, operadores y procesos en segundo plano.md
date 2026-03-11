Podemos conocer el estado de los comandos que estamos ejecutando usando lo siguiente:

```
echo $?
```

De esta forma si el estado nos devuelve un 0 significa que el estado del comando fue EXITOSO.

Podemos concatenar comandos de las siguientes maneras:
```
whoami; ls; pwd
```
con ";" hemos concatenado 3 comandos en una misma linea y la salida de estos tres comandos la veremos en la terminal

--------------


```
whoami && ls
```

El operador logico AND
De esta otra manera podemos hacer algo parecido, la diferencia es que la ejecucion del segundo comando depende de la salida exitosa del primer comando, de esta forma si el codigo de estado del primer comando es FALLIDO el segundo no se ejecutara. 

------------------

```
whoami || ls
```

El operador logico OR
En este ejemplo la linea de comando funcionara de la misma manera que el AND, con la diferencia que si el estado del primer comando es FALLIDO, aun asi el segundo comando se ejecutara, sin importar el estatus del primero.

------

# STDOUT (Standard Output) & STDERR (Standard Error)

Podemos manejar la salida por consola de tal manera que si en algun momento necesitamos controlar los errores para no mostrarlos podemos hacerlo de la siguiente manera

```
whmai 2>/dev/null
```

En este caso whoami esta mal escrito, por lo que en consola estaremos viendo un error de comando, pero con 2>/dev/null estamos redirigiendo el estado de error a un archivo considerado como "agujero negro", de esta forma en consola ya no veremos el estado del comando, unicamente si el estado es exitoso lo veremos en pantalla.

Tambien podemos redirigir todo lo que se muestre en la consola a null, esta forma es practicada en los scripts, si en algun momento ejecutamos alguna herramienta y no queremos que se muestre ninguna ejecucion en consola:

```
whoami &>/dev/null
```

-----


# Procesos en segundo plano
Cuando en una consola ejecutamos algun programa, por ejemplo:
```
wireshark
```

El proceso se ancla a la terminal, es decir que esa terminal continua ejecutando el proceso hasta que este se cierre o se finalice.
Para ejecutar el proceso en segundo plano podemos hacer lo siguiente 

```
wireshark &
```
De esta forma el proceso estara ejecutandose en segundo plano, lo que significa que la terminal funciona como el proceso "padre" y wireshark como el proceso "hijo".
El programa se ejecuta y se crea un pID, esto significa que existe ese proceso con ese ID ejecutandose en esa terminal, si nosotros cerramos la terminal, el proceso tambien finalizaria y por consecuente wireshark tambien cerraria.
Podemos desanclar el proceso de la terminal de la siguiente manera:

```
wireshark & disown
```

----
