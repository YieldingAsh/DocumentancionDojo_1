# DocumentancionDojo_1
![image](https://user-images.githubusercontent.com/99512390/234987533-304fff41-6759-43d3-a6dc-27f48a7acd59.png)
# Integrantes
- Matias Nicolas Castrellon
# Visualizacion de proyecto en SPD
![Semaforo Dojo 1](https://user-images.githubusercontent.com/99512390/234993219-87661399-d0b8-419a-a0c9-5c761ab8ef29.png)
# Descripcion
Un proyecto low cost que cumpla con las especificaciones siguientes:

1- El semáforo tiene que tener 2 leds de cada color como minimo, en caso de que uno se rompa, lo ideal serian 3.

2- Tiene que implementar los tiempos correctos como se detallan a continuación.

3- El verde dura 45 segundos.

4- El amarillo dura 5 segundos.

5- Rojo dura 30 segundos.

6- Tiene que tener señalización para personas no videntes como se detalla a continuación.

7- Durante el verde: No sonar

8- Durante el amarillo: Tiene que sonar 1 vez cada 2 segundos en un tono suave.

9- Durante el rojo: Tiene que sonar 1 vez por segundo en un tono fuerte.

Para realizar el proyecto deberán usar mínimamente:

1 ARDUINO.

1 PROTOBOARD (opcional).

6 LEDS (minimo 2 por cada color y máximo 4 para cada color).

1 BUZZER (Piezo).

RESISTENCIAS NECESARIAS PARA CADA COMPONENTE.

# Funcion principal
- Esta funcion es la funcion principar y general del programa el cual llama a las funciones parpadear() y definir() con los parametros solicitados a poner para su funcionamiento. Esta funcion es solo la encargada de ejecutar las funciones necesarias para el funcionamiento del programa.

````
void semaforo(){
	parpadear(Led_verde);
  	definir(Led_amarillo,3 ,100, 1466);
  	definir(Led_rojo,30 ,300, 800):
  	definir(Led_amarillo,3 ,100, 1466);
}
````

-Aca se utilizo #define para poder declarar pines en nombre con la variable a la cual esta asociada
````
#define Led_verde 5
#define Led_amarillo 6
#define Led_rojo 7
#define Alarma 4
````
-La funcion definir() se encarga de endender un led y llamar a la funcion alarma() asi el piezo se active durante el tiempo ingreso por parametro el cual luego apaga el led. Esta funcion por parametro enciende el led a querer e activa el piezo, recibe tambien los hercios a dar al piezo y cuanto tiempo el piezo este hasta que se apague

````
void definir(int led,int seg ,int tono, int pausa){
	digitalWrite(led, HIGH);
  	alarma(seg, tono, pausa);
	digitalWrite(led, LOW);
}
````
-La funcion parpadear() enciende un led determminado durante un tiempo determinado por pararametros sin que se active el piezo.

````
void parpadear(int led){
	digitalWrite(led, HIGH);
	delay(45000);
  	digitalWrite(led, LOW);
}
````
-La funcion alarma() enciende el piezo por 200 milisegundo y luego la apaga durante un tiempo determinado por parametro. Esta funcion por parametros recibe las veces que se activa el piezo, los hercios al piezo y por cuanto tiempo se queda apagada.

````
void alarma(int seg,int tono,int pausa){
  for (int i = 0; i < seg; i++){
  	 tone(Alarma, tono);
     delay(200);
     noTone(Alarma);
     delay(pausa);
  }
}
````



# Link del projecto

https://www.tinkercad.com/things/5grx4QoOhOr
