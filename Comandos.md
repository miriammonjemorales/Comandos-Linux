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
