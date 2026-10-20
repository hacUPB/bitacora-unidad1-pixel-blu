Hipotesis
Yo me imagino que cuando se crea un objeto Rectangulo, el computador reserva un espacio de memoria para guardar todos sus datos juntos.

Aunque Nombre viene de la clase Figura, al crear el objeto Rectangulo forma parte del mismo objeto. Es decir, la herencia hace que el Rectangulo tenga tanto sus propios datos como los que recibe de Figura.

Algo parecido a esto

Objeto Rectangulo
┌─────────────────┐
│ Nombre          │ → "Rectángulo"
├─────────────────┤
│ Base            │ → 4.0
├─────────────────┤
│ Altura          │ → 6.0
└─────────────────┘

Polimorfismo

Mi hipótesis es que cuando el programa llega a:
```C#
fig.Dibujar();
```
primero revisa qué objeto está guardado realmente dentro de fig.

Por ejemplo
fig → Circulo
       ↓
   Dibujar() de Circulo

o posiblemente

fig → Rectangulo
       ↓
   Dibujar() de Rectangulo

Creo que el programa podría tener alguna especie de referencia interna que le indica qué versión de Dibujar() debe ejecutar. Así, aunque fig sea una Figura, durante la ejecución puede saber si realmente es un Circulo o un Rectangulo.

Encapsulamiento

Yo creo que principalmente se revisa cuando estamos escribiendo o compilando el código.

Por ejemplo, si intentáramos hacer:

```C#
Figura f = new Figura(...);
f.nombre = "Hola";
```
el compilador detectaría que nombre es private y no permite acceder a él desde fuera de la clase.

Me imagino que el compilador revisa las reglas de acceso antes de convertir el código en un programa ejecutable. Por eso pienso que private funciona principalmente como una restricción del código, no como algo que el procesador tenga que estar comprobando cada vez que el programa funciona.