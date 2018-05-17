---
geometry: "top=1.0cm, bottom=1.5cm, left=2.5cm, right=2.5cm"
fontsize: 11pt
fontfamily: times
---

<div align="center">
***  

**[Módulo 2: Sistemas de Ficheros ||| Unit 2: File Systems]{.dual fontsize=huge}**   

**[Facultad de Informática, UCM]{fontsize=large}**   

**[Problemas de Sistemas Operativos ||| Operating Systems Exercises]{.dual fontsize=large}**   

***
</div>



### {.exercise}

BEGIN-SP

Calcular el número de accesos a disco necesarios (para el caso
peor y para el caso mejor) para leer 20 bloques lógicos consecutivos (no
necesariamente los 20 primeros) de un fichero en un sistema con:

a)  Asignación contigua (p.ej., ISO-9660)

b)  Asignación no contigua mediante índice enlazado (FAT)

c)  Asignación no contigua indexada (p.ej., UNIX)

**Nota**: Asumir que no hay ningún dato relacionado con el sistema de
ficheros en memoria RAM y que el fichero se encuentra en el directorio
actual. 

END-SP 

BEGIN-EN 

Calculate the number of disk accesses required
(in the worst-case and the best-case scenarios) to read 20 consecutive
logical blocks (not necessarily the first 20 blocks) of a file on a
system with:

a)  Contiguous file allocation (e.g., ISO-9660)

b)  Linked file allocation with a file allocation table (FAT)

c)  UNIX-like indexed file allocation

**Note**: Consider that no data associated with the file system can be
found in RAM. Suppose also that the file is located in the current
working directory. 

END-EN

### {.exercise}

BEGIN-SP

Un dispositivo de memoria flash de 64 MB de capacidad y bloques
de 1KB, contiene un sistema de ficheros FAT. ¿Cuántos bytes son
necesarios para almacenar la tabla FAT?

a)  64 KB

b)  128 KB

c)  1 MB

d)  512 KB

e)  Ninguna de las respuestas anteriores es correcta

¿Es posible realizar enlaces rígidos en un sistema de ficheros tipo FAT?
¿Por qué no se puede establecer enlaces rígidos a ficheros de volúmenes
distintos en sistemas de ficheros tipo EXT2? 

END-SP 

BEGIN-EN

A FAT file system with blocks of 1KB is installed on a flash memory device with 64MB of capacity. How much space is required to store the actual file
allocation table (FAT) on the device?

a)  64 KB

b)  128 KB

c)  1 MB

d)  512 KB

e)  None of the answers above are correct

Is it possible to implement hard links on a FAT-like file system? Why
hard links to files in different volumes are not feasible on an EXT2
(UNIX-like) file system ? 

END-EN

### {.exercise}

BEGIN-SP

En la siguiente figura se representa una tabla FAT. Al borde de
sus entradas se ha escrito, como ayuda de referencia, el número
correspondiente al bloque en cuestión. También se ha representado la
entrada de cierto directorio. Como simplificación del ejemplo, suponemos
que en cada entrada del directorio se almacena: Nombre de fichero, tipo (F=archivo, D=directorio), fecha de
creación y núm. del bloque inicial. 

END-SP

BEGIN-EN

@tbl:fat depicts the contents of the file allocation table
(FAT) of a file system with blocks of 512 bytes. For the sake of
clarity, the number associated with each table entry (one per block in
the FS) is shown by the corresponding cell. The contents of the file
system’s root directory are shown in @tbl:dir. For
simplicity, each directory entry features the following fields:(1) name
of the file/directory, (2) file type (F=regular file,D=directory), (3)
creation date and (4) physical block number for the first logical block
of the file. 

END-EN


<div class="columns" colsep="0.3cm">
<div class="column" width="48%">
<div fontsize="footnotesize">
| **\# Bloque** ;;; **Block \#** | **Índice** ;;; **Index** | **\# Bloque** ;;; **Block \#** | **Índice** ;;; **Index** |
| :----------------------------: | :----------------------: | :----------------------------: | :----------------------: |
|               1                |                          |               10               |                          |
|               2                |                          |               11               |                          |
|               3                |            15            |               12               |                          |
|               4                |                          |               13               |                          |
|               5                |                          |               14               |                          |
|               6                |                          |               15               |           EOF            |
|               7                |                          |               16               |                          |
|               8                |                          |               17               |                          |
|               9                |                          |               18               |                          |

: Tabla FAT ||| File-Allocation table {#tbl:fat}
</div>
</div>
<div class="column" width="48%">
<div fontsize="footnotesize">
| **Nombre** ;;; **Name** | **Tipo** ;;; **Type** | **Fecha** ;;; **Date** | **Num. Bloque** ;;; **Block number** |
| :---------------------: | :-------------------: | :--------------------: | :----------------------------------: |
|           DATA          |           F           |         8-2-05         |                  3                   |
|                         |                       |                        |                                      |
|                         |                       |                        |                                      |
|                         |                       |                        |                                      |
|                         |                       |                        |                                      |

: Directorio ||| Directory {#tbl:dir}
</div>
</div>
</div>


  




BEGIN-SP 

Considere que el tamaño de bloque en este sistema de ficheros
es 512 bytes y que el sistema operativo siempre selecciona el primer
bloque libre (número inferior) cuando se crea un fichero o se
redimensiona un fichero existente. En este supuesto, actualice el
contenido de las estructuras del sistema de ficheros tras realizar cada
una de las siguientes operaciones:

a)  Creación del fichero DATA1 con fecha 3-1-10 y tamaño 10 bytes.

b)  Creación del fichero DATA2 con fecha 3-2-10 y tamaño 1200 bytes.

c)  El archivo DATA aumenta de tamaño, necesitando 2 bloques más.

d)  Creación del directorio D con fecha 3-3-10 y tamaño 1 bloque.

e)  Creación del fichero CARDS con fecha 3-12-10 y tamaño 2 Kbytes.

END-SP

BEGIN-EN

Asumming that the operating system always selects the
first free block (lowest number) when a new file is created or an
existing file is resized, update the contents of the file system tables
to represent its final state after performing the following operations:

a)  Create a DATA1 file with date 3-1-10 and size 10 bytes.

b)  Create a DATA2 file with date 3-2-10 and size 1200 bytes.

c)  Resize the DATA file by adding two new blocks at the end of
    the file.

d)  Create a D directory with date 3-3-10 and size 1 block.

e)  Create a CARDS file with date 3-12-10 and size 2 Kbytes.

END-EN

### {.exercise}

BEGIN-SP

Un sistema de ficheros UNIX utiliza bloques de 1024 bytes y
direcciones de disco de 16 bits. Los nodos-i (entradas en una tabla que
contiene la información descriptiva de los ficheros) contienen 8
direcciones de disco para bloques de datos, una dirección de bloque
índice indirecto simple y una dirección de bloque índice indirecto
doble. ¿Cuál es el tamaño máximo de un fichero en este sistema? ¿Y el de
la partición?

END-SP

BEGIN-EN

Consider a UNIX file system that uses
blocks of 1KB and block addresses of 16 bits. Each inode of this file
system contains 8 block addresses to point to data blocks, an address to
point to a single indirect index block and another address to point to a
double indirect index block. What is the maximum file size on this file
system? What is the maximum size of the partition or volume?

END-EN

### {.exercise}

BEGIN-SP

Un programa UNIX crea un fichero e inmediatamente se
posiciona (con `lseek()`) en el byte 55 millones. Luego escribe un byte.

a)  ¿Cuántos bloques de disco ocupa ahora el fichero (incluyendo bloques
    indirectos)? Asúmase que los nodos-i contienen 10 índices directos,
    1 índice indirecto simple, 1 índice indirecto doble y 1 índice
    indirecto triple, los bloques tienen un tamaño de 2 Kbytes y el
    tamaño de los índices (direcciones de bloques de disco) es de
    32 bits.

b)  ¿Qué sucesión de índices lógicos nos lleva al byte posicionado por
    lseek?

END-SP

BEGIN-EN

A UNIX program creates a file and then places the file
position indicator (with `lseek()`) at byte 55 millions. The program then writes a byte.

a)  How many disk blocks are now used by the file (index blocks
    inclusive)? Assume that inodes contain 10 direct indexes, 1 simple
    indirect index, 1 double indirect index and 1 triple indirect index.
    Suppose further that the block size is 2KB and each index address
    (block number) occupies 32 bits.

b)  What is the sequence of logical indexes that makes it possible to
    access byte 55 millions in the file?

END-EN

### {.exercise} 

BEGIN-SP

Juan crea un fichero de nombre *JFichero*. María crea un enlace
físico a *JFichero* y le da el nombre *MFichero*. Juan elimina
*JFichero*. Luego Juan crea un nuevo fichero y también le llama
*JFichero*. ¿Cuántos ficheros diferentes existen después de las acciones
anteriores? ¿Sería diferente la respuesta si el enlace que ha creado
María fuese un enlace simbólico de nombre *MFichero* que apuntara a
*JFichero*? 

END-SP

BEGIN-EN

In an empty file system, John creates a file
named *JFile*. Then, Mary creates a hard link to *JFile* named *MFile*.
John then removes *JFile* and creates another file with the same name.
How many different files exist on the file system at this point? Would
there be the same number of different files in case that *MFile* were a
symbolic link pointing to *JFile* (instead of a hard link)? 

END-EN

### {.exercise}

BEGIN-SP 

Un sistema de ficheros basado en nodos-i y mapa de bits
contiene la siguiente información: 

END-SP 

BEGIN-EN 

A file system based
on inodes and a bitmap contains the following information: 

END-EN

![](img/structure_13.pdf){.dual width=100% alt-ext=html/.png align=center}\ 

BEGIN-SP

a)  Rellene los huecos para que el sistema sea consistente. Asuma para
    ello que el tamaño se expresa en bloques.

b)  Dibuje el árbol del directorio empleando óvalos para los
    directorios, rectángulos para los ficheros y triángulos para los
    datos

END-SP 

BEGIN-EN

a)  Assuming that the file size is specified in blocks, fill the gaps in
    the previous structures to make the file system consistent.

b)  Draw the file system directory tree hierarchy using ovals to
    represent directories, rectangles for files and triangles for data.

END-EN


### {.exercise}

BEGIN-SP

El sistema de ficheros de un SO diseñado a partir de UNIX
utiliza bloques de disco de 1024 bytes de capacidad. Para el
direccionamiento de estos bloques se utilizan punteros de 16 bits. Para
indicar el tamaño del fichero y el desplazamiento (offset) de la
posición en bytes en las operaciones read y write, se utilizan números
de 64 bits. Cada nodo-i tiene 8 punteros de direccionamiento directo, 1
puntero indirecto simple y 1 puntero indirecto doble

a)  ¿Cuál será el tamaño máximo de un fichero suponiendo despreciable el
    espacio ocupado por el superbloque y la tabla de nodos-i?

b)  Si se modifica el tamaño de puntero pasándolo a 32 bits, ¿cuál será
    el nuevo tamaño máximo?

c)  Dada la siguiente estructura de directorio[^1] indicar los
    contenidos de los directorios y nodos-i que se encontrará el sistema
    (y el orden en que se los encontrará) al hacer la búsqueda del
    fichero *mem* desde el directorio raíz. Notese que *mem* es un
    enlace físico al fichero *project*.

[^1]: Los directorios se muestran como rectángulos con bordes
    redondeados, y los ficheros como óvalos.    

END-SP 

BEGIN-EN

Consider a UNIX-like file system that uses disk blocks
of 1KB each. To represent block addresses, 16-bit pointers are used. To specify the file size as well as the offset in read and write
operations, the file system uses 64-bit numbers. Each inode has 8 direct
indexes, 1 simple indirect index and 1 double indirect index.

a)  Neglecting the space occupied by the superblock and the inode table,
    what is the maximum file size on this file system?

b)  If 32-bit pointers were used to specify block addresses, what would
    the maximum file size be now?

c)  Given the following directory hierarchy[^2], indicate the contents
    of the inodes and directories traversed by the OS when a process
    requests to open the *mem* file given its full pathname. Note that
    *mem* is a hard link to the *project* file.


[^2]: Note that directories are depicted as rectangles with rounded
    corners; ovals represent regular files. 

END-EN


![](img/tree_15.pdf){.dual alt-ext=html/.png,latex/.pdf,docx/.pdf align=center}\ 





 
