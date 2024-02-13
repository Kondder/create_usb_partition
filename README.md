CONTENIDO DE ESTE ARCHIVO
-------------------------

 * Introduccion
 * Comandos
 * Explicacion detallada


INTRODUCCION
------------
  Crear particion NTFS o FAT32 en USB

COMANDOS
---
**REQUISITO:**   Antes de empezar hay que formatear el la unidad USB a NTFS


STEP 0: Open diskpart: Windows + R --> diskpart

STEP 1:

      list disk
STEP 2:

      select disk (number of disk)
STEP 3: 

      list partition
STEP 4:

      select partition (number of partition)
STEP 5:

      shrink desired=(sizeMB)
STEP 6:

      create new primary
STEP 7:

      list partition
STEP 8:

      select partition (number new partition)
STEP 9:

        format fs=(ntfs o fat32)

STEP 10:

        assign 
        

EXPLICACION
---
Abrimos el cuadro de diálogo de Ejecutar **Windows + R**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/b973c4af-1b16-4e5d-a270-dbb77cbbff17)

Escribimos **diskpart** para abrir el intérprete de comandos diskpart que le permite administrar las unidades del equipo (discos, particiones, volúmenes o discos duros virtuales).

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/0f6c0b21-32b8-4905-a263-155b6e8abf1b)

Buscamos USB a particionar con **list disk**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/931ee8f5-7e11-4306-b83b-659444c94ba8)

Seleccionamos disco(USB) a particionar con **select disk (number of disk)**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/90b41004-1276-408f-9eae-ef0c662eab57)

Buscamos las particiones del disco seleccionado con **list partition (number of partition)**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/455e2774-7f40-4b36-bec4-e4373b46aa5c)

Seleccionamos particion a particionar con **select partition (number of partition)**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/4fc14f79-2ea0-4586-abe6-0e7b8fbdbe71)

Particionamos el disco con el comando *shrink* y el parametro *desired=size* siendo size (en MB) el tamaño de la nueva particion

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/51d73ae5-ad96-4332-a9a3-3a9a354fe950)

Creamos una particion primaria con el espacio no asignado de la nueva particion con **create partition primary**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/afacd981-d234-4a09-9b3a-d856931d73f3)

Si ahora listamos las particiones del disco(USB) veremos que una nueva particion presente con el tamaño deseado con **list partition**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/5d536b88-167e-4003-ac5b-aac00ea6785c)

Seleccionamos esta nueva particion y la formateamos a NTFS o FAT32 con **select partition (number of new partition)** y luego **format fs= (ntfs or fat32)**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/8b55f432-50af-4f38-a114-4b3849d98035)

Le asignamos una letra a esta nueva particion. Se asigna la proxima letra disponible o podes asignarle la que desees con el parametro **letter=(letter)**

![image](https://github.com/Kondder/create_usb_partition/assets/77896781/7c7350b0-842b-4286-8cf5-03ea84939ad6)
