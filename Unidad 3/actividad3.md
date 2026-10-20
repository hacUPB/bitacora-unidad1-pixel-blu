
```C++
class ofApp : public ofBaseApp {
		public:
				void setup();
				void update();
				void draw();
				void mousePressed(int x, int y, int button);
				void keyPressed(int key);
		    std::vector<Particle*> particles;
		    ~ofApp();
		private:
				void createRisingParticle();
};
```

-Hipotesis
En la memoria, el vector llamado "particles" deberia almacenar direcciones de memoria que apuntan a las particulas creadas.
Las dunciones de "setup()""upadte()""draw()", no se almacenan como datos normales dentro del objetp, mas bien, corresponde al codigo del programa
-Observable
-Conlusion