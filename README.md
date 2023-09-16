# Reto_3_DosPuntosDeVista
En este repo se hará el reto 3.
## Reto 3
El reto 3 consiste en hacer un diagrama de flujo y el psudocode de los respectivos ejercicios:
1. Plantear el algoritmo para saber si un número es primo.
2. Plantear el procedimiento matemático para hallar raices cuadradas.
---
### Procedimiento para saber si un número es primo
#### Diagrama de Flujo
Primero vamos a hacer el diagrama de flujo para que a la hora de hacer el psudocode sea mucho más fácil.
```mermaid
graph TD;
  Inicio(Inicio)--->
  Variable[n:= número el cual se probará si es primo]--->
  listaDeNúmeros[i:=lista de números de 2 hasta n**0.5]--->
  listaValor[i=2]--->
  Operacion{Residuo de n/i es igual a 0?}-- No --> CondicionalNo
  Operacion{Residuo de n/i es igual a 0?}-- Sí --> CondicionalSi
  CondicionalSi[i es divisor de n]--->
  Rta[n no es primo]--->Fin
  CondicionalNo[i no es divisor de n]--->
  Rta2[i=i+2]--->
  CondicionalFinal[i<=n**0.5?]-- Sí -->Operacion
  CondicionalFinal[i<=n**0.5?]-- No -->Rta3
  Rta3[n es primo]--->
  Fin(Fin)
```
#### Pseudocode
El pseudocode del problema sería el siguiente:
```pseudocode
[variables]
n : entero
i : número entero de lista
Inicio
  i := 2
  mientras(i<=(n**0.5)) hacer
  Si módulo(n,i) == 0 entonces
    escribir("n no es un número primo")
  Sino
    escribir("i no es divisor de n")
  i := i + 1
  Fin mientras
  escribir("i es un número primo")
Fin
```
### Procedimiento para hallar Raices Cuadradas
#### Diagrama de Flujo
Primero vamos a hacer el diagrama de flujo:
```mermaid
graph TD;
  Inicio(Inicio)--->
  Variable[n:= número al que se le sacará raiz]--->
  agrupacionVariables[Vx:= agrupación]--->
  Agrupacion[Se harán agrupaciones de dos digitos de derecha a izquierda según la cantidad de digitos de n]--->
  Pregunta{En alguna agrupación solo hay un digito?}-- No --> Resolucion
  Pregunta{En alguna agrupación solo hay un digito?}-- Sí --> Resolucion
  Resolucion[La raiz cuadrada de la primera agrupación]--->
  Rta2{La raiz es exacta?}-- Sí --> Caso1 
  Rta2{La raiz es exacta?}-- No --> Caso2
  Caso1[Ese resultado guardarlo]--->Resultado
  Caso2[Guardar el resultado de la raiz cuadrada más cercana que sea menor]--->Resultado
  Resultado{Hay más agrupaciones?}-- No --> Caso4
  Resultado{Hay más agrupaciones?}-- Sí -->Resta
  Resta[Se resta la cifra de la primera agrupación con el resultado de la raiz inferior a esa agrupación]--->
  Caso3[El resultado de la resta se une a la siguiente agrupación y será el primer digito de esa unión]--->
  Procedimiento[El resultado de la raiz cuadrada que se guardó multiplicarlo por 2]--->
  Procedimiento2[Al duplicar esa cifra se convertiran en los digitos iniciales del número que se va a multiplicar por otro para hallar el valor de la segunda agrupación]--->
  Rta3[Guardar Resultado]--->Resultado
  Caso4[El resultado guardado es la raiz de n]--->Fin
  Fin(Fin)
```
#### Pseudocode
Después del diagrama de flujo procedemos a hacer el pseudocode.
```Pseudocode
[Variables]
n:=Número entero positivo al que se le sacará raiz cuadrada
Vx:=Agrupación
x:=Número de la agrupación
D:=Digito
Inicio
  Vx(2D)
  Formar Vx de derecha a izquierda 
  Agrupación(2D-1D)
  Mientras (Vx) hacer
    Si Raiz Cuadrada exacta (Vx1) == True entonces
      Guardar(resultado)
    Sino
      Resolver (Vx1 > Raiz cuadrada exacta más cercana)
      Guardar(resultado)
      Resta(Vx1,Raiz cuadrada exacta más cercana)
      Unir D (Resultado Resta,Vx2)
      Duplicar(Resultado) == Resultado Duplicado
      Unir(Resultado Duplicado, D) == Resultado union
      Multiplicar(Resultado union, D)
  Fin mientras
Fin
```
### Ese Fue el Reto 3, espero haya sido de su agrado
*Mario Alejandro Martinez Bedoya*
