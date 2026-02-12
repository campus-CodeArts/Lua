# 05 — Funciones en Lua

## ¿Qué es una función?

Una **función** es un bloque de código que realiza una tarea concreta y que puede ejecutarse varias veces desde distintas partes del programa.

En automatización y robótica, las funciones se usan para:
- Agrupar acciones repetidas.
- Hacer el código más claro.
- Dividir un proceso complejo en partes simples.

Ejemplos típicos:
- mover a HOME
- recoger pieza
- depositar pieza
- mostrar un aviso

---

## ¿Por qué usar funciones?

Sin funciones, un programa puede volverse:
- largo,
- repetitivo,
- difícil de entender.

Con funciones:
- el código es más **legible**,
- los errores se corrigen en un solo sitio,
- el programa se parece más al proceso real.

---

## Definición básica de una función

En Lua, una función se define así:

```lua
function nombreFuncion()
    -- acciones de la función
end
```

Ejemplo sencillo:

```lua
function moverHome()
    print("Mover a HOME")
end
```

---

## Llamar a una función

Para ejecutar una función, se escribe su nombre seguido de paréntesis:

```lua
moverHome()
```

Cada vez que se llama:
- se ejecuta todo el código de la función.

---

## Funciones con parámetros

Las funciones pueden recibir **datos** para trabajar.

```lua
function moverZona(zona)
    print("Mover a zona " .. zona)
end

moverZona("A")
moverZona("B")
```

Aquí:
- `zona` es un parámetro
- la función se adapta según el valor recibido

---

## Funciones y automatización

Las funciones ayudan a representar **acciones del sistema**.

```lua
function recogerPieza()
    print("Mover a PICK")
    print("Cerrar pinza")
end

function soltarPieza(zona)
    print("Mover a zona " .. zona)
    print("Abrir pinza")
end
```

El programa principal queda mucho más claro:

```lua
recogerPieza()
soltarPieza("A")
```

---

## Funciones con retorno

Una función puede devolver un valor usando `return`.

```lua
function hayPieza()
    io.write("¿Hay pieza? (s/n): ")
    local r = io.read()
    return r == "s"
end
```

Uso:

```lua
if hayPieza() then
    print("Iniciar ciclo")
end
```

---

## Funciones y decisiones

Las funciones pueden usarse dentro de condicionales y bucles.

```lua
function leerTipoPieza()
    io.write("Tipo de pieza (A/B): ")
    return io.read()
end

local tipo = leerTipoPieza()

if tipo == "A" then
    print("Zona A")
else
    print("Zona B")
end
```

---

## Buenas prácticas con funciones

- Una función debe hacer **una sola cosa**
- Usar nombres claros (`recogerPieza`, no `f1`)
- Evitar funciones demasiado largas
- Pensar las funciones como acciones reales del sistema

---

## Errores comunes

- Crear funciones innecesarias
- Hacer funciones demasiado grandes
- No entender qué devuelve una función

Ejemplo incorrecto:

```lua
function hacerTodo()
    -- demasiadas cosas aquí dentro
end
```

---

## Mini-ejemplo completo

```lua
function moverHome()
    print("Mover a HOME")
end

function procesarPieza(tipo)
    if tipo == "A" then
        print("Depositar en zona A")
    else
        print("Depositar en zona B")
    end
end

moverHome()
procesarPieza("A")
moverHome()
```

---

## Objetivo

Al terminar este archivo deberías poder:
- Explicar qué es una función.
- Crear y llamar funciones en Lua.
- Usar parámetros y valores de retorno.
- Entender cómo las funciones mejoran la claridad del código.
