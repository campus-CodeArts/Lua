# 07 — Retos de práctica en Lua (automatización y robótica)

Este archivo contiene una serie de **retos teóricos y prácticos** para afianzar los conceptos vistos sobre:

- Variables.
- Condicionales.
- Bucles.
- Funciones.
- Tablas.

---

### Reto 1 — Elección de bucle

Te piden que programes un robot que **revise continuamente si hay una pieza disponible** y solo actúe cuando la detecte.

**Pregunta:** 

¿Qué tipo de bucle utilizarías (`while`, `repeat/until` o `for`)?  
Justifica brevemente tu respuesta.

---

### Reto 2 — Condicionales

Un robot debe:

- moverse a la zona A si la pieza es de tipo A,
- moverse a la zona B si la pieza es de tipo B,
- mostrar un aviso si el tipo es desconocido.

**Pregunta:**  

¿Qué estructura condicional utilizarías y por qué?

---

### Reto 3 — Variables y estados

Explica con tus palabras para qué serviría una variable llamada:

```lua
estadoSistema
```

en un programa de automatización.

---

### Reto 4 — Funciones

¿Por qué es recomendable usar funciones para representar acciones como las siguientes?

- Mover a HOME.
- Recoger pieza.
- Soltar pieza.

Indica al menos **dos ventajas**.

---

### Reto 5 — Tablas

¿En qué casos usarías una **tabla** en lugar de varias variables sueltas?  
Pon un ejemplo relacionado con robótica o automatización.

---

### Reto 6 — Variables y condicionales

Crea un bloque de código que:

- declare una variable `hayPieza`,
- muestre por pantalla si el robot debe **esperar** o **iniciar el ciclo**.

Prueba su funcionamiento en el compilador online.

---

### Reto 7 — Bucle de espera

Crea un fragmento de código que:

- pregunte repetidamente si hay una pieza disponible,
- termine solo cuando el usuario indique que sí hay pieza.

Prueba su funcionamiento en el compilador online.

---

### Reto 8 — Función sencilla

Crea una función llamada `moverHome()` que cuando sea llamada muestre por pantalla:

```text
Mover a posición HOME
```

---

### Reto 9 — Función con parámetro

Crea una función llamada `depositarPieza(zona)` que cuando sea llamada:

- reciba una zona (`A` o `B`),
- muestre por pantalla dónde se deposita la pieza.

Ejemplo de uso esperado:

```lua
depositarPieza("A")
depositarPieza("B")
```

---

### Reto 10 — Clasificación de piezas

Crea un programa que:

1. Pregunte si hay una pieza disponible.
2. Si no hay pieza, muestre un mensaje de espera.
3. Si hay pieza:
   - pida el tipo de pieza (`A` o `B`),
   - decida a qué zona moverla,
   - vuelva a HOME.
4. El proceso debe poder repetirse varias veces.

No es necesario que sea perfecto, pero debe reflejar la lógica completa. Prueba su funcionamiento en el compilador online.

---

### Reto 11 — Uso de tablas

Crea una tabla que represente el estado de un robot con al menos:

- Estado actual.
- Número de piezas procesadas.

Muestra ambos valores por pantalla en el compilador online.

---

### Reto 12 — Identificación de estructuras

Observa el siguiente fragmento de código:

```lua
while sistemaActivo do
    if hayPieza then
        print("Procesar pieza")
    end
end
```

**Pregunta:**  

¿Qué estructuras de programación aparecen en el código?  
Explica brevemente la función de cada una.

---

### Reto 13 — Orden de ejecución

Explica qué ocurre **primero** y qué ocurre **después** en un programa que contiene:

- Declaraciones de variables.
- Un bucle principal.
- Funciones definidas al inicio.

Pista: Piensa como se van definiendo las variables y funciones cuando se ejecuta código en Lua

---

### Reto 14 — Condición mal planteada

Un técnico escribe la siguiente condición:

```lua
if tipoPieza == "A" or "B" then
```

**Pregunta:**  

¿Es correcta esta condición?  
Si no lo es, explica por qué y cómo debería plantearse.

---

### Reto15 — Uso de funciones

Indica en qué casos **NO tendría sentido** usar una función en un programa de automatización.

---

### Reto 16 — Variables de control

¿Por qué es importante usar una variable como `sistemaActivo` para controlar la ejecución de un programa automático?

---

### Reto 17 — Bucles infinitos

¿Qué problemas puede causar un bucle infinito en un sistema real automatizado?  
Indica al menos **dos riesgos**.

---

### Reto 18 — Contador de ciclos

Crea un programa que:
- Cuente cuántos ciclos ha realizado el sistema.
- Muestre el número por pantalla en cada iteración.
- Se detenga tras 5 ciclos.

---

### Reto 19 — Control de acceso

Crea un bloque de código que:

- Pida una contraseña por consola.
- Permita continuar solo si la contraseña es correcta.
- Muestre un mensaje de error en caso contrario.

---

### Reto 20 — Función de aviso

Crea una función llamada `mostrarAviso()` que muestre un mensaje de alarma por pantalla.  
Llama a la función cuando una condición se cumpla.

---

### Reto 21 — Decisión múltiple

Crea un programa que:

- Pida el tipo de pieza (`A`, `B` o `C`).
- Muestre un mensaje distinto para cada tipo.
- Muestre un aviso si el tipo no es válido.

---

### Reto 22 — Espera activa

Crea un programa que:
- Permanezca esperando hasta que el usuario indique que el sistema puede arrancar.
- Muestre un mensaje de espera mientras tanto.

---

### Reto 23 — Uso combinado de funciones y bucles

Crea un programa que:

- Utilice una función para simular una acción del robot.
- Llame a esa función dentro de un bucle.
- Repita la acción varias veces.

---

### Reto 24 — Mini sistema automático

Crea un programa que simule un sistema automático sencillo con:

- Una variable de estado.
- Al menos una función.
- Un bucle principal.
- Una decisión basada en una condición.

Describe brevemente qué proceso representa tu programa.