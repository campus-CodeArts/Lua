# 03 — Condicionales en Lua

## ¿Qué es un condicional?

Un **condicional** permite que un programa **tome decisiones**.  
Según si una condición se cumple o no, el programa ejecuta unas instrucciones u otras.

En automatización y robótica, los condicionales se usan constantemente para:
- Comprobar sensores.
- Decidir acciones.
- Gestionar errores o estados de espera.

Ejemplos típicos:
- ¿Hay pieza?
- ¿El sistema está activo?
- ¿El tipo de pieza es A o B?

---

## La estructura básica `if`

La forma más sencilla de un condicional en Lua es:

```lua
if condicion then
    -- acciones si la condición es verdadera
end
```

Ejemplo:

```lua
local hayPieza = true

if hayPieza then
    print("Hay pieza disponible")
end
```

Si `hayPieza` es `true`, se ejecuta el bloque.  
Si es `false`, se ignora.

---

## Condicional con alternativa: `if / else`

Cuando queremos ejecutar **una cosa u otra**, usamos `else`.

```lua
if condicion then
    -- acciones si la condición es verdadera
else
    -- acciones si la condición es falsa
end
```

Ejemplo típico en automatización:

```lua
local hayPieza = false

if hayPieza then
    print("Mover a posición PICK")
else
    print("Permanecer en espera")
end
```

---

## Comparaciones más comunes

Las condiciones suelen basarse en **comparaciones**.

### Comparadores habituales

- `==`  igual
- `~=`  distinto
- `<`   menor que
- `>`   mayor que
- `<=`  menor o igual
- `>=`  mayor o igual

Ejemplo:

```lua
local piezas = 3

if piezas == 3 then
    print("Se han procesado 3 piezas")
end
```

---

## Condicionales con texto (strings)

También se pueden comparar textos.

```lua
local tipoPieza = "A"

if tipoPieza == "A" then
    print("Depositar en zona A")
else
    print("Depositar en zona B")
end
```

Esto es muy habitual en clasificación de piezas.

---

## Condicionales encadenados (`if / elseif / else`)

Cuando hay **más de dos opciones**, se usa `elseif`.

```lua
if condicion1 then
    -- acciones
elseif condicion2 then
    -- acciones
else
    -- acciones por defecto
end
```

Ejemplo:

```lua
local estado = "ERROR"

if estado == "HOME" then
    print("Robot en posición inicial")
elseif estado == "PICK" then
    print("Robot recogiendo pieza")
elseif estado == "PLACE" then
    print("Robot depositando pieza")
else
    print("Error: Estado desconocido")
end
```

---

## Condicionales con entradas simuladas

En este bloque, muchas decisiones se basan en lo que introduce el usuario.

```lua
io.write("¿Hay pieza? (s/n): ")
local respuesta = io.read()

if respuesta == "s" then
    print("Hay pieza, iniciar ciclo")
else
    print("No hay pieza, esperar")
end
```

Aquí:
- `respuesta` simula un sensor
- el `if` decide el comportamiento del sistema

---

## Buenas prácticas con condicionales

- Las condiciones deben ser **claras y simples**
- Usar variables con significado real
- Evitar condicionales innecesariamente largos
- Mantener la lógica legible

---

## Errores comunes

- Usar `=` en lugar de `==`
- Comparar texto sin comillas
- Condiciones demasiado complejas

Ejemplo incorrecto:

```lua
if tipoPieza = A then
    print("Error")
end
```

---

## Mini-ejemplo completo

```lua
local sistemaActivo = true
local hayPieza = false

if sistemaActivo then
    if hayPieza then
        print("Mover a PICK")
    else
        print("Sistema activo pero sin pieza")
    end
else
    print("Sistema detenido")
end
```

---

## Objetivo

Al terminar este archivo deberías poder:
- Explicar qué es un condicional.
- Usar `if`, `else` y `elseif`.
- Comparar números y texto.
- Tomar decisiones en función de variables y entradas.