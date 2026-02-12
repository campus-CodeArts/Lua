# 02 — Variables en Lua

## ¿Qué es una variable?

Una **variable** es un espacio donde se guarda información que el programa puede usar y modificar mientras se ejecuta.

En automatización y robótica, las variables se usan para representar:
- Estados del sistema.
- Información de sensores.
- Contadores.
- Decisiones del proceso.

Ejemplos típicos:
- hayPieza
- tipoPieza
- estado
- contador

---

## Declaración de variables en Lua

En Lua, las variables se crean simplemente asignándoles un valor.

```lua
local hayPieza = false
local contador = 0
```

La palabra **local** indica que la variable solo existe dentro del programa o bloque donde se define.

Usaremos siempre `local` para evitar errores y confusiones.

---

## Tipos de variables más usados

### 1) Variables booleanas (verdadero / falso)

Se usan para condiciones y decisiones.

```lua
local sistemaActivo = true
local aguaCaliente = false
```

Valores posibles:
- true
- false

---

### 2) Variables numéricas

Se usan para contadores, tiempos, ciclos, etc.

```lua
local piezasProcesadas = 0
local tiempoEspera = 5
```

---

### 3) Variables de texto (strings)

Se usan para mensajes, estados o tipos.

```lua
local tipoPieza = "A"
local mensaje = "Sistema en espera"
```

Las cadenas de texto van entre comillas.

---

## Asignación y modificación de variables

Una variable puede cambiar su valor durante la ejecución del programa.

```lua
local contador = 0

contador = contador + 1
contador = 10
```

Esto es muy común en automatización:
- contar ciclos,
- cambiar estados,
- activar o desactivar condiciones.

---

## Variables y decisiones

Las variables suelen usarse dentro de condiciones.

```lua
local hayPieza = true

if hayPieza then
    print("Hay pieza disponible")
else
    print("No hay pieza")
end
```

Veremos estas condiciones y como funcionas más adelante.

---

## Variables y entradas simuladas

En este bloque simulamos entradas usando consola.

```lua
io.write("¿Hay pieza? (s/n): ")
local respuesta = io.read()

if respuesta == "s" then
    hayPieza = true
else
    hayPieza = false
end
```

Aquí:
- Respuesta guarda lo que escribe el usuario.
- hayPieza representa el estado del sensor

---

## Buenas prácticas con variables

- Usar nombres claros (hayPieza, no x)
- No reutilizar variables para cosas distintas
- Inicializar las variables antes de usarlas
- Pensar qué representa cada variable en el proceso real

---

## Errores comunes

- Usar una variable sin inicializar  
- Usar nombres poco claros  
- Mezclar números y texto sin querer  

Ejemplo incorrecto:

```lua
contador = contador + 1   -- contador no estaba inicializado
```

---

## Mini-ejemplo completo

```lua
local sistemaActivo = true
local piezas = 0

while sistemaActivo do
    print("Piezas procesadas: " .. piezas)
    piezas = piezas + 1

    if piezas == 3 then
        sistemaActivo = false
    end
end

print("Proceso terminado")
```

---

## Objetivos

Al terminar este archivo deberías poder:
- Explicar qué es una variable y para qué sirve.
- Crear variables booleanas, numéricas y de texto.
- Modificar el valor de una variable durante el programa.
- Usar variables dentro de condiciones y bucles.
