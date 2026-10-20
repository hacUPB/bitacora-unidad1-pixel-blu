1. Encapsulamiento
```C#
public double Radio { get; private set; }
```
Aquí se puede consultar el Radio desde fuera, pero solo la propia clase puede modificarlo.

1.2 Privado y Public
Porque así se controla cómo se puede acceder al dato. Si nombre fuera público, cualquier parte del programa podría cambiarlo directamente y provocar errores.

Con la propiedad Nombre se permite acceder al dato, pero manteniendo cierto control sobre su modificación. Es como tener el dato guardado dentro de la clase y ponerle una "puerta" para acceder a él.

2. Herencia

Herencia en `Circulo`
```C#
public class Circulo : Figura
```

`Figura` significa que `Circulo` hereda de la clase `Figura.`
Por eso Circulo recibe características y métodos que ya existen en Figura, como Nombre y Dibujar().

2.2 Además de Radio, ¿qué otros datos almacena un Circulo gracias a la herencia?

El círculo también tiene el dato Nombre, que viene de Figura.

En este caso, cuando se crea:

```C#
public Circulo(double radio) : base("Círculo")
```

se está enviando "Círculo" a la clase padre Figura, que lo guarda en Nombre.

Entonces el objeto Circulo tiene, en resumen:

Radio = propio de Circulo.
Nombre = heredado de Figura.

También hereda el método Dibujar(), aunque en este caso Circulo lo reemplaza con su propia versión.

3. Polimorfismo
¿Cómo creo que funciona fig.Dibujar() por debajo?

Yo creo que el programa primero sabe que fig es una Figura, pero también revisa qué tipo de objeto tiene realmente guardado en ese momento.

```C#
fig.Dibujar();
```
SI fig contiene un Circulo, ejecuta el Dibujar() de Circulo.

Si contiene un Rectangulo, ejecuta el Dibujar() de Rectangulo.

Esto es posible porque Dibujar() está declarado como abstract en Figura y cada clase hija tiene su propia versión con override.

En otras palabras, la variable es de tipo Figura, pero el programa identifica qué figura específica tiene y utiliza el comportamiento correspondiente.