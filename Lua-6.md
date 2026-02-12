# 06 — Tablas en Lua (arrays asociativos)

## ¿Qué es una tabla en Lua?

Una **tabla** es la estructura de datos principal de Lua.  
Sirve para **guardar varios valores relacionados** dentro de una misma variable.

En Lua, las tablas pueden usarse como:
- Listas (arrays).
- Diccionarios (arrays asociativos).
- Estructuras de datos más complejas.

En automatización y robótica, las tablas se usan para:
- Representar estados.
- Agrupar parámetros.
- Asociar acciones a decisiones.

---

## Crear una tabla sencilla (lista)

Ejemplo de tabla tipo lista:

```lua
local zonas = { "A", "B", "C" }

print(zonas[1])
print(zonas[2])
```

En Lua, los índices empiezan en **1**, no en 0.

---

## Tablas como arrays asociativos

Las tablas pueden usar **claves con nombre**, no solo números.

```lua
local robot = {
    estado = "HOME",
    piezas = 0,
    activo = true
}

print(robot.estado)
print(robot.piezas)
```

Esto se parece mucho a una “estructura” en otros lenguajes.

---

## Modificar valores de una tabla

Los valores de una tabla pueden cambiarse durante la ejecución.

```lua
robot.estado = "PICK"
robot.piezas = robot.piezas + 1
```

Esto es muy útil para representar el **estado del sistema**.

---

## Tablas para representar estados del sistema

Ejemplo típico de automatización:

```lua
local sistema = {
    estado = "ESPERA",
    hayPieza = false
}
```

Luego se puede usar en condicionales:

```lua
if sistema.estado == "ESPERA" then
    print("Sistema en espera")
end
```

---

## Tablas y bucles

Las tablas pueden recorrerse con bucles.

```lua
local zonas = { "A", "B", "C" }

for i = 1, #zonas do
    print("Zona: " .. zonas[i])
end
```

El operador `#` indica el número de elementos de la tabla.

---

## Uso típico en robótica y simulación

En simulación y control es habitual usar tablas para:
- Agrupar parámetros de un robot.
- Definir posiciones (HOME, PICK, PLACE).
- Gestionar estados y transiciones.

Ejemplo conceptual:

```lua
local posiciones = {
    HOME = "Posición inicial",
    PICK = "Recogida",
    PLACE_A = "Zona A",
    PLACE_B = "Zona B"
}

print(posiciones.HOME)
```

---

## Buenas prácticas con tablas

- Usar tablas para agrupar información relacionada
- Elegir nombres claros para las claves
- No mezclar demasiados tipos de datos sin necesidad
- Pensar la tabla como una “estructura del sistema”

---

## Errores comunes

- Olvidar que los índices empiezan en 1
- Acceder a una clave que no existe
- Usar tablas cuando una variable simple es suficiente

Ejemplo incorrecto:

```lua
print(zonas[0])   -- índice incorrecto
```

---

## Mini-ejemplo completo

```lua
local robot = {
    estado = "HOME",
    piezas = 0
}

robot.estado = "PICK"
robot.piezas = robot.piezas + 1

print("Estado: " .. robot.estado)
print("Piezas: " .. robot.piezas)
```

---

## Objetivo

Al terminar este archivo deberías poder:
- Explicar qué es una tabla en Lua.
- Usar tablas como listas y como arrays asociativos.
- Acceder y modificar valores de una tabla.
- Entender cómo las tablas ayudan a estructurar un programa.
