# entregagrupal

La dirección de github de este repositorio es: [ github](https://github.com/jzazooro/entregagrupal/edit/main/README.md)

### Ejercicio 01: Sucesor de un día de la semana

**Tipo DIA estructura:**
* (lunes, martes, miércoles, jueves, viernes, sábado, domingo)
fin DIA

**Algoritmo: Definición de sucesor por enumeración**

```
sucesor(día : DIA) : DIA
    # El sucesor de `día' en la semana.
 
Realización
    siguiendo el valor de día hacer
    	= 'lunes' :
            Resultado ← 'martes'
    	= 'martes' :
            Resultado ← 'miércoles'
    	= 'miércoles' :
            Resultado ← 'jueves'
    	= 'jueves' :
            Resultado ← 'viernes'
    	= 'viernes' :
            Resultado ← 'sábado'
    	= 'sábado' :
            Resultado ← 'domingo'
    	= 'domingo' :
            Resultado ← 'lunes'
        si no
        	Nada
    fin hacer
 
postcondición
	día = 'lunes' => Resultado = 'martes'
	día = 'martes' => Resultado = 'miércoles'
	...
fin sucesor
```

### Ejercicio 02: Colocar dos numerosrespecto a su suma y a su producto
**Algoritmo clasificar:**
   * Clasifica a, b, c, y d en orden creciente.
    
**Entrada**
   * a, b, c, d : T → COMPARABLE
    
**precondición**
   * VERDADERO
    
**realización**
```
    clasificar3(a, b, c)
    # a ≤ b ≤ c ; situar `d'
    si
        d < a
    entonces
        # a > d ; b ≤ c
        intercambiar(a, d)
        # a ≤ d ; b ≤ c
    fin si
    # a ≤ d ; b ≤ c
    clasificar3(b, c , d)
    # a ≤ b ≤ c ≤ d
postcondición
    a ≤ b ≤ c ≤ d
fin clasificar4
```

### Ejercicio 03 = Cálculo del importe del descuento
**Algoritmo importe_descuento**

**entrada**
Precio : **REAL**
* coste de un producto

Descuento: (precio : **REAL**) : **REAL**
* Importe del descuento acordado sobre “precio”.

**precondición**
Precio >= 0

**Realización**
```
    si
        precio < 100,00
    entonces
        # precio < 100,00 => no hay descuento
        Resultado ← 0,00
    si no si
        precio < 500
    entonces
        * 100 ≤ precio < 500 => descuento del 5 %
        Resultado ← precio x 0,05
    si no
        # precio ≥ 500 => descuento del 8 %
        Resultado ← precio x 0,08
    fin si
```

**postcondición**

Precio < 10000  - **Resultado** = 0.00

100 <= precio < 500 - **Resultado** = precio x 0.05

500 <= precio - **Resultado** = precio x 0.08

**fin importe_descuento**

### Ejercicio 5 = Cálculo del importe del descuento para una familia dada en ADIF

Algoritmo = calculo_descuento

**entrada**

Precio = **REAL**
* Coste de un producto

Descuento: (precio : **REAL**) : **REAL**
* Importe del descuento acordado sobre “precio”.

Hijos: **ENTERO**
* Número de hijos de una familia


**precondición**

Precio >= 0

**Realización**
``` 
    si
        hijos = 0    
    entonces
        precio = precio => no hay descuento
        Resultado ← precio
    si
        hijos = 1    
    entonces
        precio = precio*0.9 =>descuento de 10%        
        Resultado ← precio*0.9
    si
        hijos = 2    
    entonces
        precio = precio*0.85 =>descuento de 15%        
        Resultado ← precio*0.85
    si
        hijos = 3   
    entonces
        precio = precio*0.82 =>descuento de 18%        
        Resultado ← precio*0.82
    si
        hijos = 3+n   
    entonces
        precio = precio*0.82-n/100 =>descuento de 18%        
        Resultado ← precio*0.82-n/100
   fin
```
**Postcondición**
..
**fin calculo_descuento**

### Ejercicio 06: Descuento de microprocesadores

**Algoritmo de coste**

**Entrada**

   * Numero de chips: Entero #Numero de chips que desea comprar
   * Empresa: cadena # empresa a la que pertenece
   
**Variable**

   * Descuento chips: Entero # descuento que se te aplica por el número de chips
   * Descuento empresa: Entero # descuento que se te aplica por ser de una empresa
   
**Resultado: Entero**

   * Descuento: Entero #Descuento total que se aplica a la compra
   
**Realización:**

```
     Si número de chips>10000 y chips<20000
     Entonces tu descuento será del 10%
     Si número de chips>20001 y chips<40000 
     Entonces tu descuento será del 15%
     Si número de chips>41000
      Entonces tu descuento será del 20%
     Descuento total= descuento chips más* descuento empresa
````

## Ejercicio 07: Viaje escolar

**Algoritmo viaje_escolar:**
   * Cálculo del precio de coste por alumno
   * Cálculo del cote global del viaje en función de la cantidad de alumnos
   
**entrada**
   * numero de alumnos: ENTERO
   * numero de días: ENTERO
   
**Resultado: REAL**

**variable**
   * coste del trayecto por alumno: REAL
   * coste del alojamiento por alumno: REAL
   * coste de la comida por alumno: REAL
   * coste del trayecto total: REAL
   * coste de la comida total: REAL
   * coste del alojamiento total: REAL
   * coste total por alumno: REAL
   * coste global: REAL
   
**realización**

```
   coste de la comida por alumno ← 3,50€
   si
	numero de alumnos > 25
   entonces
	coste del trayecto por alumno ←  61,00€
   si no
	coste del trayecto por alumno ← 67,30€
   si	
	numero de alumnos <= 30
   entonces
	coste del alojamiento por alumno ← 4,75€
   si no
 	si
		31 <= numero de alumnos <= 35
	entonces
		coste del alojamiento por alumno ← 4,00€
   si no
	coste del alojamiento por alumno ← 3,50€
	coste del trayecto total ← coste del trayecto por alumno * numero de alumnos
	coste del alojamiento total ← coste del alojamiento por alumno * numero de alumnos
	coste de la comida total ← coste de la comida por alumno * numero de alumnos
	coste global ←  coste del trayecto total + coste del alojamiento total + coste de la comida total
	coste total del alumno ←  coste de la comida por alumno + coste del alojamiento por alumno + coste de la comida por alumno
   fin si
   …
  ```
**postcondicion**
	* fin viaje_escolar


### Ejercicio 08: Prima anual
**Algoritmo prima anual:**
  * Importe de la prima anual en función del número
  * de accidentes, de la distancia recorrida y de la antigüedad
  * del conductor
  
**entrada**
  * accidentes: ENTERO # Número de accidentes
  * distancia : ENTERO # Distancia recorrida
  * antigüedad : ENTERO # Antigüedad
  
**Resultado: REAL**
**variable:**
  * prima_antigüedad : REAL
  * prima_distancia : REAL
  
**realización**
```
si
  accidentes > 3
entonces
  Resultado ← 0,00
si no
  # Cálculo de la prima de antigüedad
si
  antigüedad < 4
entonces
  prima_antigüedad ← 0,00
si no
  prima_antigüedad ← 200,00 +  REAL(antigüedad – 4) x 20,00
fin si
  # cálculo de la prima de rendimiento
   prima_distancia ← inf(REAL(distancia) x 0,01, REAL(400))

  # Cálculo de la prima anual
fin si
```
**postcondición**
	* fin prima_anual

