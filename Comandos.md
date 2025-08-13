1. Para ver las opciones de un comando.
```
nombre del comando --help
```
2. Para ver el manual de un comando.
man + nombre del comando
ej:
```
man journalctl
```
3. Cuando el comando del que quieres ver el manual coincide con otro tipo de orden por ejemplo con una función se utiliza:
```
man man
```
Te saldrá un menú con las opciones para que introduzcas man + nº de la opción + nombre del comando.

NOTA: la Linux fundation permite usar –help y man  en los exámenes.

4. Buscar un comando cuando no lo recuerdas:

Usamos apropos + el comienzo del comando

Ej:
```
apropos director
```

(nos buscara comandos q empiecen así incluido directory y directories.

NOTA: la primera vez que ejecutemos el comando apropos deberemos ejecutar el comando “sudo mandb”
apropos -s 1,8 director

5.  Crear hard link:
```

```
6.  Crear soft link:
```

```
7.  Cambiar grupo:
```
chgrp group_name file/directory
```
ej:

<img width="600" height="71" alt="image" src="https://github.com/user-attachments/assets/3aa567f5-8341-48aa-b331-36d1dbe1c86e" />


```
chgrp sudo family_dog.jpg
```
<img width="580" height="94" alt="image" src="https://github.com/user-attachments/assets/d246c043-1c60-4ab6-a185-58c9329468b1" />

NOTA: solo podemos cambiar a grupos de los que nuestro usuario forma parte. Salvo el usuario root que puede cambiar a cualquier grupo del sistema.

8.  Para ver los grupos:
```
groups
```
9.  Cambiar el propietario de un archivo o directorio:
```
sudo chown jane family_dog.jpg
```

NOTA: para poder cambiar el propietario al no serlo nosotros deberemos cambiar a root usando sudo delante del comando.

10.  Cambiar propietario y grupo:
```
sudo chown aaron:family family_dog.jpg
```
11.  Para ver los permisos de un archivo

<img width="872" height="103" alt="image" src="https://github.com/user-attachments/assets/19c214e0-cc79-4072-8472-532dea8fdc0c" />

La primera letra: empezando por la izquierda nos indica si es un archivo, un directorio, un directorio especial... Una "d"seria un directorio, una "l" sería un soft link, o un guión para un archivo regular.

<img width="402" height="320" alt="image" src="https://github.com/user-attachments/assets/1ec6fdba-9223-432c-9953-52d260b8f721" />

Los siguientes nueve caracteres nos muestran los permisos. Los primeros 3 caracteres nos indican el propietario, el siguiente grupo de tres nos indican los permisos del grupo, y los tres ultimos para otros usuarios, cualquier usuario que no sea desde el que lo estas consultando o del grupo.

<img width="535" height="212" alt="image" src="https://github.com/user-attachments/assets/d0cf1763-4c12-4209-98ae-ab05d4b2be29" />

Las letras significan lo siguiente:

<img width="278" height="211" alt="image" src="https://github.com/user-attachments/assets/fbca4bd1-094d-4be1-a400-8917021b75a0" />

12.  Para cambiar los permisos:
```
chmod permissions file/directory
```
Ejemplo queremos cambiar los permisos para el usuario para que tenga permisos de escritura:
```
chmod u+w family_dog.jpg
```
<img width="455" height="324" alt="image" src="https://github.com/user-attachments/assets/535d7f75-2b97-453a-9ffb-a0963c349d40" />

13.  Para eliminar permisos:
```
chmod permissions file/directory
```
Ejemplo: queremos cambiar los permisos de otros usuarios para que no tengan permisos de escritura:
```
chmod o-r family_dog.jpg
```

<img width="443" height="325" alt="image" src="https://github.com/user-attachments/assets/e3872a86-afad-4911-8ea8-40ce9edde2c8" />

14.

```
chmod permissions file/directory
```
Ejemplo: queremos asegurarnos de que solo el grupo pueda leer este archivo:
```
chmod g=r family_dog.jpg
```
NOTA: Si pusieramos el mismo comando pero sin ninguna letra detrás de el igual, lo que haría sería eliminar todos los permisos para el grupo.

<img width="451" height="313" alt="image" src="https://github.com/user-attachments/assets/7b9098fc-610d-4211-8927-e39f3e63467e" />

15.  Otro comando que hace lo mismo pero siguindo otra lógica.
```

```

Ejemplo: queremos eliminar todos los permisos del grupo.
```
chmod g-rwx family_dog.jpg
```

16.  Podemos cambiar los permisos de usuario, grupo y otros usuarios en el mismo comando.
```

```
Ejemplo: queremos que el usuario pueda leer y escribir en el archivo, el grupo leer y otros usuarios no puedan hacer nada.
```
chmod u+rw,g=r,o= family_dog.jpg
```

17. Otro comando para ver los permisos.
    
    <img width="720" height="148" alt="image" src="https://github.com/user-attachments/assets/26335b8a-def3-4983-96af-22b34a6d3842" />

19.  Establecer permisos a través de valores octales.

<img width="450" height="142" alt="image" src="https://github.com/user-attachments/assets/780252c3-e114-4c99-979d-d4d02cb5c881" />

Cada letra se traduce en un 0 o en 1. Si hay letra es un "1" si no hay nada, es decir aparece un guión es "0".

Tabla de referencia para conversión:

<img width="258" height="317" alt="image" src="https://github.com/user-attachments/assets/58c565f6-fef0-44cd-bc0b-e6312d91ab90" />

Por lo tanto en los tres primeros digitos que pertenecen a los permisos de usuario, según la foto tendríamos:
1
1
0
que si lo buscamos en la tabla sería 110 = 6.
Para permisos de grupo tendríamos 
1
0
0
que si lo buscamos en la tabla equivaldría a 100 = 4.
Y por último para permisos de otros usuarios tendríamos.
0
0
0
que equivaldría según la tabla a 0.

Otra forma sería con la tabla octal: 

<img width="268" height="155" alt="image" src="https://github.com/user-attachments/assets/3bfc6eb1-4122-4eb9-9a7f-98a4613a4a6c" />

Ejemplo:

<img width="475" height="102" alt="image" src="https://github.com/user-attachments/assets/61eb11bc-09ce-4898-9b69-2fd428004409" />

A cada letra se le asigna un valor.
Para los servicios de usuario tenemos:
"r" que equivaldría a 4 según la tabla.
y 
"w" que equivaldría a 2.
como no tiene permisos de ejecución equivaldría a un 0.

Por lo tanto quedaría para el usuario como "420". se sumaria : 4+2+0=6
Para el grupo "400", se sumaría 4+0+0=4
y para otros "000" , 0+0+0=0

Ejemplo: queremos asignar permisos 640:
```
chmod 640 family_dog.jpg
```

20.  SUID: es un permiso especial que permite a los usuarios ejecutar un ejecutable con los permisos del propietario del ejecutable.

Para poder proporcionar a un archivo los permisos SUID. Ejecutaremos el siguiente comando donde el número "4" nos indica permisos SUID.
    
```
chmod 4664 suidfile
```
Si hacemos un ls para ver los permisos del archivo podemos ver que en el lugar donde debería estar el execute aparece una "S" mayúscula, esto indica que están activados los permisos SUID y que no tiene permisos de ejecucción. (sin embargo si la "s" fuera minúscula tendría activo el SUID y permisos de ejecución).

<img width="647" height="64" alt="image" src="https://github.com/user-attachments/assets/bd78c019-6839-42e7-85a9-e96967707fd1" />

    
21.  SGID: es un permiso similar pero se aplica tanto a ejecutables como a directorios.

Para poder proporcionar a un archivo los permisos SGID. Ejecutaremos el siguiente comando donde el número "2" nos indica permisos SGID.
```
chmod 2664 sgidfile
```
Si hacemos un ls para ver los permisos del archivo podemos ver una "S" mayúscula en dónde deberían estar los permisos de ejecución para  el grupo.  Esta "S" nos indica que estan activados los permisos SGID y al ser mayúscula nos indica que no estan activos los permisos de ejecución para el grupo. Si fuera minúscula indicaría que estan activos los permisos de ejecucción y SGID.

22.  Sticky Bit: permiso especial que se puede establecer en directorios y restringe la eliminación de archivos en ese directorio.
    
 NOTA: solo el propietario del archivo, el propietario del directorio o el superusuario root pueden eliminar los archivos.


23.  Para buscar que archivos tienen:
```
find .-perm /4000
```
NOTA: nos buscaría los archivos con permisos SUID

```
find .-perm /2000
```
NOTA: nos buscaría los archivos con permisos SGID

24.  Si quisieramos dar permisos SUID Y SGID a un mismo archivo:
```
chmod 6664 both
```
se haria 4 de los permisos SUID + 2 de los permisos SGID = 6 (el seis que aparece empezando por la izquierda en el comando).


25.  En el sticky Bit los permisos son diferentes y solo podrán eliminar los archivos el usuario, el propietario y root.
```
chmod +t stickydir/
```
o
```
chmod 1777 stickydir/
```

Si hacemos ls aparecerá una "T" mayúscula  en la opción de ejecución para otros usuarios si esta desativada la ejecución pero activados los permisos sticky bit. Por el contrario será una "t" minúscula si está activa la ejecución y los permisos sticky bit.

