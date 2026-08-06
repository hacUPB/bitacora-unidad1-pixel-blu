 1. Identifica una instrucción que use la ALU y explica qué hace.

Una instrucción que utiliza la **ALU** es:

D=D-A

Esta instrucción realiza una resta entre el valor almacenado en el registro D y el registro A. El resultado se guarda nuevamente en D. En el programa se usa para comparar direcciones de memoria y decidir si debe continuar llenando o borrando la pantalla.


2. ¿Para qué sirve el registro PC?

El PC (Program Counter) es el registro que almacena la dirección de la siguiente instrucción que ejecutará la CPU. Normalmente aumenta automáticamente después de cada instrucción, pero cuando el programa encuentra una instrucción de salto (`JMP`, `JNE`, `JGE`, `JLE`, etc.), el PC cambia a la dirección indicada por la etiqueta correspondiente.

3. ¿Cuál es la diferencia entre `@i` y `@READKEYBOARD`?

@i hace referencia a una variable almacenada en la memoria RAM. Se utiliza para guardar la posición actual de la pantalla que el programa está modificando.
@READKEYBOARD hace referencia a una etiqueta del programa. No almacena datos; representa la dirección de una instrucción a la que el programa puede saltar para repetir el ciclo de lectura del teclado.

4. Describe qué se necesita para leer el teclado y mostrar información en la pantalla.

Para leer el teclado se accede a la dirección `KBD` (24576), donde se almacena el estado del teclado. Si el valor es distinto de cero, significa que hay una tecla presionada.

Para mostrar información en la pantalla se escriben valores en la memoria de video que comienza en la dirección `SCREEN` (16384). Escribir `-1` en una posición enciende los píxeles correspondientes (negro), mientras que escribir `0` los apaga (blanco).

5. Identifica un bucle en el programa y explica su funcionamiento.

El bucle principal comienza en la etiqueta:

(READKEYBOARD)

Al finalizar cada iteración, el programa ejecuta:

```asm
@READKEYBOARD
0;JMP
```
Este salto incondicional hace que el programa vuelva continuamente a la etiqueta `READKEYBOARD`, permitiendo leer el teclado una y otra vez y actualizar la pantalla según el estado de las teclas.

6. Identifica una condición en el programa y explica su funcionamiento.

Una condición del programa es:

@KBD
D=M
@KEYPRESSED
D;JNE

Esta condición verifica si el contenido de `KBD` es diferente de cero.

 Si `D ≠ 0`, significa que hay una tecla presionada y el programa salta a la etiqueta `KEYPRESSED` para comenzar a llenar la pantalla.
 Si `D = 0`, el salto no se realiza y el programa continúa borrando la pantalla.
