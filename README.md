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
postcondición

fin prima_anual

