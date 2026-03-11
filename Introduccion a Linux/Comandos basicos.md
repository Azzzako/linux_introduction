```
whoami
```

Te permite averiguar que usuario es el que se encuentra en la sesión actual.

```
id
```

Te permite listar la serie de grupos a los que pertenece el usuario actual.

```
sudo su
```

Te permite escalar el privilegio del usuario actual al usuario root. 
El usuario root es el usuario tiene mayor privilegio a nivel de sistema.

```
sudo
```

Permite realizar instrucciones de forma privilegiada sin convertirte directamente en usuario root.

```
cat
```

Se utiliza para listar el contenido de los archivos.

```
echo
```

Se utiliza para imprimir algo en la consola.

```
echo $PATH
```

Un ejemplo seria el anterior, te permite imprimir el PATH del sistema, el PATH es una lista de carpetas en la que el sistema busca un programa para ejecutar un comando.
Ejemplo: 

```
# Va a buscar el comando ls a la lista de carpetas para ejecutar la instruccion
ls -la
```

------------------------------------------------------------------------
```
grep
```

Se utiliza para aplicar filtros a una salida para encontrar dentro del archivo

Puntos importantes a considerar en la primera parte:
Que es el PATH?
Rutas relativas y absolutas.
Gestion de usuarios y grupos en LINUX.


```
pwd
```

print work directory: imprime directorio de trabajo actual.


```
which
```
```
command -v
```


which te permite conocer la ruta absoluta de un binario, conocer su ubicacion.
en dado caso que which no este disponible puedes usar el segundo, sirve exactamente igual

```
ls
```

Sirve para listar los archivos dentro de un directorio.


```
cd
```

"change directory" Se utiliza para moverse entre directorios.

