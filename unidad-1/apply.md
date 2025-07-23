# Unidad 1

## 🛠 Fase: Apply

## Actividad 5:

Rectangulo que cambia de color al presionar un botón (A en este caso)

En primer lugar recordemos que un sistema físico interactivo es el conjunto de Inputs, Procesamiento y Outputs; en este caso podemos dividir estos componentes dentro del programa:

Inputs: En este caso los botones generan la interacción y el mismo Micro:Bit es el que envía la información al programa.
Proceamiento: Diría es el programa p5js pues es quien interpreta los datos.
Outputs: Recibimos el estímulo visual del cambio de color en el rectángulo.

### 🧭 Resumen paso a paso – ¿Cómo funciona el código?

1. **micro:bit (MicroPython)**
   - Se configura el puerto serial con `uart.init()`.
   - Dentro de un bucle infinito:
     - Si el botón A está presionado, se envía `"A"`.
     - Si no, se envía `"N"`.
   - Estos datos se transmiten al computador por USB cada 100 milisegundos.

2. **p5.js (JavaScript)**
   - Se crea un canvas y un botón para conectar el micro:bit.
   - Cada vez que se recibe un dato:
     - Si es `"A"`, cambia el color de relleno a **rojo**.
     - Si es `"N"`, cambia a **verde**.
   - El rectángulo se dibuja en el centro del canvas con el color correspondiente.

3. **Interacción visual**
   - El usuario presiona o suelta el botón A.
   - El sistema responde en tiempo real con un cambio de color.
   - Esta es la manifestación del **output** en el sistema interactivo.

---


## Actividad 6:
### Escribe el enlace a tu programa en el editor de p5.js.

[Mueve la bola](https://editor.p5js.org/DanielAMendozaJ/sketches/4E8K_HAig)


### Copia el código de tu programa en la bitácora (recuerda insertarlo usando markdown y el lenguaje javascript).

```javascript
let port;
let connectBtn;
let connectionInitialized = false; // Abrió el puerto de comunicaciones
let circleX;

function setup() {
  createCanvas(400, 400);
  background(220);

  circleX = width / 2;

  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(80, 300);
  connectBtn.mousePressed(connectBtnClick);
}

function draw() {
  background(220);

  if (port.opened() && !connectionInitialized) {
    port.clear();
    connectionInitialized = true;
  }

  if (port.availableBytes() > 0) {
    let dataRx = port.read(1);

  if (dataRx == "I") {
      // Aquí se pone mover a la izquierda
      circleX -= 10;
    } else if (dataRx == "D") {
      // Aquí se pone mover a la derecha
      circleX += 10;
    }
  }

  // Limitar el movimiento al tamaño del canvas
  circleX = constrain(circleX, 0, width);

  // Dibujar el círculo
  fill("rgb(255,0,254)");
  noStroke();
  ellipse(circleX, height / 2, 50, 50);

  // Cambiar texto del botón según estado
  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
  } else {
    connectBtn.html("Disconnect");
  }
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
    connectionInitialized = false;
  } else {
    port.close();
  }
}
```

### Copia el código del micro:bit en la bitácora (recuerda insertarlo usando markdown y el lenguaje python).

```python
from microbit import *

uart.init(baudrate=115200)
display.show(Image.DIAMOND)

while True:
    if button_a.is_pressed():
        uart.write('I') # Mover Izquierda
    if button_b.is_pressed():
        uart.write('D') # Mover Derecha
    else:
        uart.write('N')  # Enviar 'N' si no se presiona ningún botón (indiferente)
    sleep(100)
```
