
## Funciones

  
### MPI_Send

  

Parametros

  

```c

MPI_Send(mensaje, longitud_mensaje, tipo_de_datos, destinatario, etiqueta, comunicador)

```

  

- mensaje

- longitud mensaje

- tipo de datos

- destinatario

- etiqueta

- comunicador

  

### MPI_Recv

  

```c

MPI_Recv(mensaje, longitud mensaje, tipo de datos, remitente, etiqueta, comunicador)

```

- mensaje

- longitud mensaje

- tipo de datos

- remitente

- etiqueta

- comunicador

## Comandos

  

### mpicc

Es un envoltorio para el compilador de C que añade automáticamente las banderas, rutas y bibliotecas necesarias para compilar programas MPI.

  

### mpicc -showme

  

Esta opción muestra las banderas y opciones que mpicc añadiría si fuera a compilar un programa, pero sin realmente compilar nada. Es útil para entender qué se está añadiendo al comando de compilación o para depuración.

```

mpicc -showme

```

  

**Ejemplo output**:

```

gcc -I/usr/local/include -pthread -L/usr/local/lib -Wl,-rpath -Wl,/usr/local/lib -Wl,--enable-new-dtags -lmpi

```

- gcc: El compilador de C subyacente.

- I/usr/local/include: Incluye los archivos de cabecera ubicados en /usr/local/include.

- pthread: Añade soporte para multithreading con hilos POSIX.

- L/usr/local/lib: Busca bibliotecas en /usr/local/lib.

- Wl,-rpath -Wl,/usr/local/lib: Añade /usr/local/lib al rpath, permitiendo al sistema encontrar las bibliotecas compartidas en tiempo de ejecución.

- Wl,--enable-new-dtags: Utiliza "nuevas etiquetas dinámicas" para rpath.

- lmpi: Enlaza la biblioteca MPI.

  
  

### mpicc -showme:compiler

  

El comando mpicc -showme:compiler muestra solo las opciones de compilación (-I/usr/local/include -pthread) que se añadirían si estuvieras compilando un programa con mpicc. Esta información puede ser útil si estás tratando de entender qué banderas están siendo utilizadas o si estás intentando depurar un problema de compilación.

  
  

## Compilación

  

### Wrapper

  

```

sudo gcc mpiHello.c -o mpiHello -pthread -L/usr/local/lib -Wl,-rpath -Wl,/usr/local/lib -Wl,--enable-new-dtags -lmpi

```

  

### Directamente con gcc

```

sudo mpicc mpiHello.c -o mpiHello

```

  

## Ejecución

  

### Linux

  

```

mpirun -np 4 mpiHello

```

  

### WSL

  

```

mpirun -np 4 ./mpiHello

```
