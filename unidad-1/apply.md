# Unidad 1

## 🛠 Fase: Apply




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
