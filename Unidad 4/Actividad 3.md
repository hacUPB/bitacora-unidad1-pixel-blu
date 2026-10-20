Configura 
```C++
viewportglViewport(0, 0, bufferWidth, bufferHeight);
```

con
```C++
glViewport(0, bufferHeight/2, bufferWidth/2, bufferHeight/2);
```

Cambia los valores de bufferWidth y bufferHeight: divide por 2, por 4, multiplica por 2, por 4, etc. ¿Qué pasa? ¿Qué observas? ¿Qué crees que está pasando?. 

Que pasa?
Dividir por 2: hace que el area del dibujo sea reducida a la mitad
Dividi por 4: El area se vuelve todavia mas pequeña
Multiplicar por 2: El area del dibujo aumenta y ocupa mas espacio que la ventana
Multiplicar por 4: El area puede extenderse mucho mas alla de los limites visibles. parte de la imagen queda fuera de la ventana

Que observo?
Al cambiar los valores de  
```C++
bufferWidth
```

```C++
bufferHeight
```
la imagen cambia de tamaño y de posición. Cuando los valores disminuyen, el área visible se hace más pequeña; cuando aumentan, la imagen puede extenderse fuera de la ventana.


Que creo?
creo que esto sucede porque 
```C++
glViewport() 
```
utiliza las coordenadas y dimensiones que le damos para determinar cómo se representa la escena dentro de la ventana. Si modificamos estos valores, cambiamos el área de dibujo, pero no necesariamente la posición o el tamaño real de los objetos en el mundo 3D.