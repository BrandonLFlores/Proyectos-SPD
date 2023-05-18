# Primer parcial SPD

- Nombre: Brandon Flores
- Materia: SPD
- Profesores: Esteban Quiroz y Gianni Maggiori

---
## Parte Práctica Domiciliaria

![](diseño.png)

---
### Descripción
Lo que simula este circuito es un montacarga, a medida que va subiendo de piso, se muestra en el display en cuál se ecuentra. Los leds verde y rojo indican si el montacarga está en movimiento o en pausa. Y con los botones controlamos si este sube, baja, o se queda parado en alguno de los pisos.

---
## Función principal
- Al apretar el botón "Sube", empieza el circuito subiendo piso a piso, va desde el piso número 0, hasta el piso número 9 (a lo que llega el display).

- Para parar en alguno de los pisos, tenemos el botón "Stop/Play". En cualquier piso que querramos frenar, lo apretamos y ahí se queda, hasta que nosotros le indiquemos que continúe.

- Y por último, para bajar, el botón "Baja". Cuando lo apretemos, el montacarga empezará a bajar, ya sea que  esté en el último piso, o esté en pausa en alguno.

- Display: En el display 7 segmentos se irá mostrando en qué piso se encuentra el circuito.

- En movimiento: Cuando el circuito esté en movimiento, se encenderá el led verde.

- En pausa: Cuando el circuito se encuentre frenado, se encenderá el led rojo.

---
## Porcion del codigo
```c++
void Semaforo()
{
  void loop()
  {
  if(digitalRead(Boton) == LOW)
  {
      while(digitalRead(Boton) != LOW)
      {
      PrendeYApaga(Led_C,0,1,1,0,0,0,0);
      PrendeYApaga(Led_S,1,1,0,1,1,0,1);
      PrendeYApaga(Led_I,1,1,1,1,0,0,1);
      PrendeYApaga(Led_M,0,1,1,0,0,1,1);
      PrendeYApaga(Led_I,1,1,1,1,0,0,1);
      PrendeYApaga(Led_S,1,1,0,1,1,0,1);
      }
  }

  }  
  void PrendeYApaga(int Led,int a,int b,int c,int d,int e,int f,int g)
  {
  digitalWrite(Led,HIGH);
  digitalWrite(A,a);
  digitalWrite(B,b);
  digitalWrite(C,c);
  digitalWrite(D,d);
  digitalWrite(E,e);
  digitalWrite(F,f);
  digitalWrite(G,g);
  tone(Buzzer,500,500);
  delay(5000);
  digitalWrite(Led,LOW);
  digitalWrite(A,0);
  digitalWrite(B,0);
  digitalWrite(C,0);
  digitalWrite(D,0);
  digitalWrite(E,0);
  digitalWrite(F,0);
  digitalWrite(G,0);
  delay(5000);
  }
}
```

---
## Link al proyecto

[tinkercard.com](https://www.tinkercad.com/things/hdnTTYVUAlF)