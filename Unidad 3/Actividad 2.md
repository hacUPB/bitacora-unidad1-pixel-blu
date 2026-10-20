    La aplicación simula fuegos artificiales utilizando programación 
    orientada a objetos. Existe una clase base Particle que define el 
    comportamiento general de las partículas. 
    A partir de ella se crean diferentes tipos de partículas, 
    como las que suben y las que aparecen durante una explosión. 
    Una RisingParticle comienza en la parte inferior de la pantalla y se mueve 
    hacia una posición aleatoria en la parte superior. Cuando alcanza cierta 
    altura o supera su tiempo de vida, se marca para explotar. ofApp 
    detecta esto, elimina la partícula original y genera entre 20 y 30 nuevas 
    partículas de un tipo de explosión elegido aleatoriamente. 
    Estas nuevas partículas se desplazan, se vuelven transparentes con el tiempo,
    finalmente desaparecen. El usuario puede generar partículas haciendo clic, 
    crear muchas con la barra espaciadora y guardar capturas con la tecla S.