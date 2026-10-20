
1. @SCREEN

   Predicción: El registro **A tomará la dirección inicial de la memoria de la pantalla (16384).
   Resultado: El registro A quedó con el valor 16384.

2. D=A

   Predicción: El valor almacenado en A se copiará al registro D.
   Resultado: El registro D tomó el valor 16384.

3. @i

   Predicción: El registro A apuntará a la dirección de memoria donde está la variable i.
   Resultado: El registro A cambió a la dirección asignada a i.

4. M=D

   Predicción: El valor de D se almacenará en la variable i.
   Resultado: La variable i quedó con el valor 16384.

5. (READKEYBOARD)

   Predicción: El programa marcará el inicio del ciclo de lectura del teclado.
   Resultado: La ejecución continuó desde esa etiqueta.

6. @KBD

   Predicción: El registro A tomará la dirección del teclado (24576).
   Resultado: El registro A quedó con el valor 24576.

7. D=M

   Predicción: El registro D almacenará el estado del teclado.
   Resultado: Si no había teclas presionadas, D valía 0; si había una tecla, tomaba un valor distinto de 0.

8. D;JNE

   Predicción: Si una tecla está presionada, el programa saltará a la etiqueta KEYPRESSED.
   Resultado: El salto solo ocurrió cuando el teclado tenía un valor distinto de 0.

9. @i D=M @SCREEN D=D-A

   Predicción: El programa comparará el valor de * con el inicio de la memoria de pantalla.
   Resultado: La comparación determinó si aún había posiciones por borrar.

10. @READKEYBOARD, D;JLE

    Predicción: Si la pantalla ya estaba completamente borrada, el programa volverá a leer el teclado.
    Resultado: El salto se realizó cuando i era igual o menor que SCREEN.

11. @i, M=M-1, A=M, M=0

    Predicción: Se disminuirá i y se escribirá un 0 en esa posición de la memoria de video para borrar parte de la pantalla.
    Resultado: La pantalla comenzó a limpiarse gradualmente.

12. (KEYPRESSED)

    Predicción: Si se detectó una tecla presionada, el programa continuará desde esta sección.
    Resultado: La ejecución entró en el bloque encargado de llenar la pantalla.

13. @i, D=M, @KBD, D=D-A

    Predicción: Se verificará si ya se llegó al final de la memoria de pantalla.
    Resultado: La comparación evitó escribir fuera del área de video.

14. @READKEYBOARD, D;JGE

    Predicción: Si la pantalla ya está completamente llena, el programa volverá a leer el teclado.
    Resultado: El salto ocurrió cuando i alcanzó el límite.

15. @i, A=M, M=-1

    Predicción: Se escribirá -1 en la memoria de video para encender 16 píxeles.
    Resultado: La pantalla comenzó a llenarse de negro.

16. @i, M=M+1

    Predicción: La variable i avanzará a la siguiente posición de memoria de la pantalla.
    Resultado: El programa quedó listo para modificar la siguiente palabra de la memoria de video.

17. @READKEYBOARD, 0;JMP

    Predicción: El programa volverá al inicio del ciclo para seguir verificando el teclado.
    Resultado: La ejecución se repitió continuamente, permitiendo llenar o borrar la pantalla según el estado del teclado.
