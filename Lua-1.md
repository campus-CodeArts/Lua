# 01 — ¿Qué es Lua? (background y usos habituales)

## ¿Qué es Lua?

**Lua** es un lenguaje de programación **ligero**, **rápido** y **fácil de integrar** en otras aplicaciones. A menudo no se usa como “lenguaje principal” de un sistema, sino como un lenguaje de **scripting** (guiones) para añadir lógica y comportamiento a programas más grandes.

Ideas clave:
- Es **interpretable** (no necesitas compilar como en C/C++).
- Es **pequeño** y se integra muy bien dentro de otros programas.
- Es muy usado para **automatizar comportamientos**, **controlar lógica** y **prototipar**.

---

## Un poco de historia

Lua nació en Brasil en los años 90, con el objetivo de ser:
- **portable** (funcionar en muchos sistemas),
- **embebible** (fácil de integrar en otros programas),
- y con una sintaxis sencilla para escribir lógica.

---

## ¿Para qué se usa Lua normalmente?

Lua se utiliza mucho cuando necesitamos un lenguaje que sea:
- sencillo para escribir reglas y comportamientos,
- rápido en ejecución,
- fácil de insertar dentro de un software existente.

### Usos habituales

#### 1) Videojuegos y lógica de gameplay
Muchos motores y juegos usan Lua para:
- eventos, misiones, diálogos,
- reglas de comportamiento,
- scripts de IA sencilla.

#### 2) Simulación y robótica
Lua es común en simuladores porque permite:
- controlar objetos del simulador con scripts,
- programar secuencias, estados y condiciones,
- prototipar automatismos antes de ir a un entorno real.

> En CoppeliaSim, por ejemplo, es habitual programar scripts en Lua para controlar el comportamiento de robots y sensores.

#### 3) Automatización y configuración
En algunos sistemas Lua se usa para:
- archivos de configuración “inteligentes”,
- reglas de negocio,
- flujos de control sencillos.

#### 4) Sistemas embebidos
Por ser ligero, Lua se usa también en entornos con recursos limitados.

---

## ¿Por qué aprender Lua en este bloque?

En automatización y robótica, la mayor dificultad no suele ser el lenguaje, sino la **lógica**:
- secuencias,
- condiciones,
- repetición,
- estados,
- lectura de entradas / ejecución de acciones.

Lua es perfecto para aprender esto porque:
- tiene una sintaxis **simple**,
- se lee casi como pseudocódigo,
- y se usa en herramientas reales de simulación.

---

## Cómo se ejecuta Lua en este curso

En este bloque usaremos Lua de forma **guiada**:

- Ejecutaremos programas en un **compilador online**.
- Simularemos entradas (sensores) con `io.read()`.
- Simularemos acciones del sistema con `print()`.

Esto permite centrarnos en lo importante:
> **pasar de un proceso → a lógica → a código**

---

## Ejemplo mínimo

```lua
print("Hola, Lua")

local nombre = "Gonzalo"
print("Bienvenido a CodeArts, " .. nombre)
```