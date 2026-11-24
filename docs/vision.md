# Visión y Alcance — Medidor (Fase 0)

## 1. Visión del proyecto

Poder medir objetos prácticamente en cualquier lugar usando solo el teléfono móvil y algún objeto cotidiano de medida normalizada conocida, devolviendo siempre la medida acompañada de su incertidumbre (`valor ± incertidumbre`) y ejecutándose completamente en local sobre Android.

## 2. Alcance de la v1

- **Incluido en v1:**
  - **N1:** Largo y ancho de objetos planos sobre una superficie plana.
  - **N2:** Perímetro, área, ángulos y distancias entre puntos en el plano.
  - **N3:** Objetos 3D sencillos (cilindros, esferas, cajas) y alturas.
- **Extensiones planificadas (fuera de v1 inicial):**
  - **N4:** Objetos definidos por el usuario y vista en vivo / realidad aumentada.
  - **N5:** Personas (opcional).

## 3. Métricas de éxito

- **Precisión objetivo (condiciones controladas):** error medio absoluto (MAE) `< 1 mm` en objetos de hasta `10 cm` sobre superficie plana.
- **Calibración de incertidumbre:** el intervalo `valor ± incertidumbre` debe cubrir el valor real (medido con calibre) de forma consistente en el set de evaluación.
- **Paridad:** el núcleo nativo en el dispositivo debe reproducir los resultados del núcleo de referencia en Python dentro de la tolerancia definida.

## 4. Convenciones

- **Unidades:** milímetros (`mm`) internamente y en salidas numéricas por defecto; áreas en `mm²` y ángulos en grados (`°`).
- **Sistema de coordenadas:**
  - Imagen: origen `(0, 0)` en la esquina superior izquierda, `x` hacia la derecha, `y` hacia abajo (en píxeles).
  - Plano rectificado / mundo 2D: origen en la esquina de referencia o centro definido por la homografía, ejes en `mm`.
- **Formato de salida:** estructura tipada con `value`, `uncertainty`, `unit`, `confidence` y referencias utilizadas (representación legible: `valor ± incertidumbre unidad`).

## 5. Política del catálogo de referencias

- Añadir una referencia nueva al catálogo debe consistir únicamente en añadir datos YAML, sin modificar código.
- **Requisitos obligatorios por cada entrada:**
  1. Identificador único (`id`).
  2. Dimensiones oficiales en `mm`.
  3. **Tolerancia** documentada (`tolerance_mm`).
  4. **Fuente oficial o estándar** (`source`, p. ej. ISO/IEC 7810, Banco Central Europeo).
- Cualquier entrada sin fuente o sin tolerancia debe ser rechazada por el validador del catálogo.
