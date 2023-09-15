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
graph TD
    Inicio(Inicio)--->
    Variable[n:= número el cual se probará si es primo]--->
    listaDeNúmeros[i:=lista de números de 2 hasta n**0.5]--->
    listaValor[i=2]--->
    Operacion{¿Residuo de n/i es igual a 0?}-- No --> CondicionalNo
    Operacion{¿Residuo de n/i es igual a 0?}-- Sí --> CondicionalSi
    CondicionalSi[i es divisor de n]--->
    Rta[n no es primo]--->Fin
    CondicionalNo[i no es divisor de n]--->
    Rta2[i=i+2]--->
    CondicionalFinal[¿i<=n**0.5?]-- Sí -->Operacion
    CondicionalFinal[¿i<=n**0.5?]-- No -->Rta3
    Rta3[n es primo]--->
    Fin(Fin)
```
#### Pseudocode
El pseudocode del problema sería el siguiente:
#### Psudo
