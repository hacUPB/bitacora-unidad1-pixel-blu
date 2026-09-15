
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
En la memoria, el vector deberia almacenar direcciones de memoria que apuntan a las particulas creadas  
-Observable
-Conlusion