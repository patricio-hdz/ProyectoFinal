## Consideraciones para los códigos

Para correr el script que genera matrices hay que correr el siguiente código:

```
gcc -Wall -fopenmp GeneraMatrices.c -o GeneraMatrices.out
```

Posteriormente se tiene que correr el siguiente código con los parámetros deseados:

```
./GeneraMatrices.out #renglones #columnas ArchivoconMatriz.txt
```

Para correr el script que multiplica matrices de manera secuencial hay que correr el siguiente código:

```
gcc -Wall -fopenmp multip_secuencial.c -o multip_secuencial.out
```

Posteriormente se tiene que correr el siguiente código con los parámetros deseados, es importante mencionar que se deben tener los archivos A.txt y B.txt en la misma carpeta:

```
./multip_secuencial.out dimMatA dimMatB
```

Para correr poder obtener las tablas de resultados se corre el archivo *machine.sh* siguiendo los pasos:

1. Escribir en el archivo las access keys de aws para poder generar una máquina remota (para esto es necesario tener una cuenta de aws), las access keys se llenan en esta parte del script:

```
#Cargamos las llaves para aws
export MACHINE_DRIVER=amazonec2
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
export AWS_DEFAULT_REGION=us-west-2
export AWS_INSTANCE_TYPE=m4.2xlarge
export AWS_SUBNET_ID=subnet-c321398b
export AWS_VPC_ID=vpc-1e4bca67
```

Como vemos para el proyecto se utilizó una máquina m4.2xlarge con 8 cpu's y 32GB de memoria RAM, se puede cambiar por otro tipo de máquina. Una vez que se llenaron las credenciales se ejecuta de la siguiente manera:

```
sudo chmod +x prueba.sh
./prueba.sh
```
Al ejecutar correrá los programas y creará los archivos de resultados. Para poder ver los resultados se creó una carpeta de Dropbox para la cual la pantalla pedirá un access token, el access token es el siguiente:

```
Jv6JnjSKugAAAAAAAAAAe0RZ5Z6X-b4igzf9P94g_ecj8CQR4h_Cx3T2tSq2ycO8
```
Pedirá la confirmación del token, a lo que respondemos que si (Y+enter) y así cargará los datos a dropbox, el código fuente para poder realizar este proceso está en la siguiente liga: Dropbox-Uploader[https://github.com/andreafabrizi/Dropbox-Uploader]
