Al ejecutar el programa en el simulador, la CPU ejecuta las instrucciones una por una. 
Primero carga el número 1 en el registro D, luego carga el número 2 y realiza la suma. 
El resultado obtenido es 3, el cual se almacena correctamente en la dirección RAM16.

Después de guardar el resultado, el programa entra en un bucle infinito mediante las
 instrucciones @END y 0;JMP. Esto hace que el procesador permanezca ejecutando 
 continuamente esas dos instrucciones sin modificar nuevamente la memoria.

 La memoria ROM (Read Only Memory) almacena el programa o las instrucciones que 
 ejecuta la CPU. Su contenido no cambia durante la ejecución del programa y permanece
fijo mientras el programa está cargado.

La memoria RAM (Random Access Memory) almacena los datos con los que trabaja el
 programa, como variables, resultados de operaciones y valores temporales. Su contenido 
 puede modificarse continuamente mientras el programa se ejecuta. 