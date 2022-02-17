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
**Algoritmo clasificar4**
    * Clasifica `a', `b' `c' y `d' en orden creciente.
    
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

postcondición

fin prima_anual
```
