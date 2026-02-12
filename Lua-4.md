# 04 — Bucles en Lua

## ¿Qué es un bucle?

Un **bucle** permite repetir un conjunto de instrucciones **varias veces** mientras se cumpla una condición.

En automatización y robótica, los bucles son fundamentales para:
- Comprobar sensores continuamente.
- Mantener el sistema en espera.
- Repetir ciclos de trabajo.
- Implementar procesos automáticos continuos.

Ejemplos típicos:
- Esperar hasta que haya pieza.
- Repetir un ciclo mientras el sistema esté activo.
- Contar piezas procesadas.

---

## Bucle `while`

El bucle más usado en automatización es `while`.

### Estructura básica

```lua
while condicion do
    -- acciones que se repiten
end
```

El bucle se ejecuta **mientras la condición sea verdadera**.

---

### Ejemplo sencillo

```lua
local sistemaActivo = true
local contador = 0

while sistemaActivo do
    print("Ciclo número: " .. contador)
    contador = contador + 1

    if contador == 3 then
        sistemaActivo = false
    end
end
```

---

## Uso típico en automatización

Un sistema automático suele funcionar **de forma continua** hasta que se detiene.

```lua
local sistemaActivo = true

while sistemaActivo do
    print("Sistema en funcionamiento")

    -- aquí se comprobarían sensores y estados

    sistemaActivo = false  -- solo para este ejemplo
end
```

---

## Bucle `repeat / until`

Este bucle ejecuta el código **al menos una vez** y repite hasta que la condición se cumpla.

### Estructura

```lua
repeat
    -- acciones
until condicion
```

---

### Ejemplo: esperar hasta que haya pieza

```lua
local hayPieza = false

repeat
    io.write("¿Hay pieza? (s/n): ")
    local r = io.read()
    if r == "s" then
        hayPieza = true
    end
until hayPieza

print("Pieza detectada")
```

---

## Diferencia entre `while` y `repeat`

| while | repeat |
|------|--------|
| Comprueba la condición **antes** | Comprueba la condición **después** |
| Puede no ejecutarse nunca | Se ejecuta al menos una vez |
| Muy usado en control continuo | Útil para esperas activas |

---

## Bucle `for` (menos usado en automatización)

Lua también tiene `for`, pero se usa menos en control de procesos.

### Ejemplo

```lua
for i = 1, 5 do
    print("Iteración " .. i)
end
```

Se usa más para:
- recorrer listas,
- repetir un número fijo de veces.

---

## Bucles infinitos (con control)

En automatización es habitual un bucle “infinito” con condición de salida.

```lua
local sistemaActivo = true

while true do
    print("Sistema funcionando")

    io.write("¿Parar sistema? (s/n): ")
    local r = io.read()

    if r == "s" then
        break
    end
end
```

`break` permite salir del bucle.

---

## Buenas prácticas con bucles

- Asegúrate de que el bucle **puede terminar**
- Controla bien las condiciones
- Evita bucles infinitos sin control
- Usa bucles para representar ciclos reales del sistema

---

## Errores comunes

- Condiciones que nunca cambian
- Bucles infinitos sin salida
- Usar `for` cuando se necesita `while`

Ejemplo incorrecto:

```lua
while true do
    print("Nunca termina")
end
```

---

## Mini-ejemplo completo

```lua
local sistemaActivo = true
local ciclos = 0

while sistemaActivo do
    print("Ciclo " .. ciclos)
    ciclos = ciclos + 1

    if ciclos == 5 then
        sistemaActivo = false
    end
end

print("Proceso terminado")
```

---

## Objetivo

Al terminar este archivo deberías poder:
- Explicar qué es un bucle.
- Usar `while`, `repeat / until` y `for`.
- Elegir el bucle adecuado para un proceso automático.
- Evitar bucles infinitos no controlados.
