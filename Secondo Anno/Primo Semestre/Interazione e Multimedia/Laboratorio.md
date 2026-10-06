La canvas è raffigurabile tramite un piano cartesiano.
- i valori di default della canvas è 100 x 100 px
## FUNZIONI
- **size(int,int)** $\to$ definisce la grandezza della canvas
- **background(int), background(int, int, int)** $\to$ definisce il colore dello sfondo della canvas, con un solo parametro usa la scala dei grigi, con 3 parametri usa RGB
- **point(float x, float y)** $\to$ disegna un pixel nel punto $(x,y)$
- **line(float x_1, float y_1, float x_2, float y_2)** $\to$ disegna una linea da $(x_{1},y_{1})$ a $(x_{2},y_{2})$
- **ellipse(float x, float y, float d_x, float d_y)** $\to$ disegna un ellisse nel punto $(x,y)$ con diametro da $x=d_x$ e diametro da $y=d_{y}$
- **rect(float x, int l1, int l2, int l3)**  $\to$ crea un rettangolo, $x=$ posizione angolo altro a sinistra
- **stroke(int), stroke(int,int,int)** $\to$ definisce il colore delle linee designate dal momento dell'istanza
- **ellipseMode(CENTER), ellipseMode(CORNER), ellipseMode(RADIUS), ellipseMode(CORNERS)** $\to$ modifica come il terzo e il quarto parametro vengono interpretati
- **width** $\to$ variabile che restituisce il valore della larghezza della canvas
- **height** $\to$ variabile che restituisce il valore dell'altezza della canvas
- **fill(int), fill(int,int,int), fill(int,int,int,int)** $\to$ riempe le forme definite dopo l'istanza di fill, a 4 parametri si aggiunge una variabile $\alpha$ che indica la trasparenza
- **circle(float x, float y, float d_x)** $\to$ disegna un cerchio in $(x,y)$ con diametro $d_{x}$
- **nostroke()** $\to$ non disegna la circonferenza delle forme
- **get(x,y)** $\to$ 
- **print()** 
- **println()**
- **strokeWeight(int)** $\to$ definisce lo spessore dello stroke, il parametro può andare da 0 a $+\infty$
> Il canale $\alpha$ si applica anche a stroke e tutte le funzioni che si ritornano un colore.

>Per definire una variabile colore si usa color nome = color(int,int,int) o il valore esadecimale


