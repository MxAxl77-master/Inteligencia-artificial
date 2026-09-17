# Bloque 1 — ¿Qué dataset necesitamos?

## P1 — ¿Morirá en el siguiente frame?

### 1. Variable objetivo

La variable objetivo podría llamarse:

`died_next_frame`

Sería de tipo **binaria**, porque solo tendría dos valores:

- `0`: no morirá
- `1`: sí morirá

La columna `died` actual no sirve directamente porque indica si murió en ese mismo frame.

### 2. Variables de entrada

Usaría principalmente:

- `speed`: velocidad del juego.
- `obstacle_type`: tipo de obstáculo.
- `dist_obstacle`: distancia al obstáculo.
- `jump`: si el dinosaurio está saltando.
- `dino_y`: altura del dinosaurio.

Estas variables ayudan a saber si el dinosaurio puede chocar en el siguiente momento.

### 3. Granularidad

Para este problema usaría **un frame por fila**.

Esto es necesario porque queremos predecir lo que pasará en el siguiente frame.

### 4. Tamaño mínimo

Consideraría unas **500 partidas o más**.

Esto permitiría tener suficientes ejemplos de momentos donde el dinosaurio muere y donde sobrevive.

### 5. Riesgo

Un riesgo sería usar la columna `died` directamente.

Eso haría que el modelo aprenda si el dinosaurio ya murió, no si va a morir en el siguiente frame.

También sería un problema no guardar la altura del dinosaurio, porque `jump = 1` no nos dice qué tan alto está.