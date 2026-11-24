# 📏 Medidor

> Aplicación **Android** (Flutter) que mide objetos a partir de una fotografía usando como referencia objetos cotidianos de **tamaño normalizado** (tarjetas, monedas, billetes, folios, etc.), con estimación de incertidumbre y fusión de varias referencias. El núcleo de visión se desarrolla y valida en **Python** y se ejecuta **en local, en el móvil**.

Consulta [ROADMAP.md](ROADMAP.md) para el plan completo por fases y [docs/vision.md](docs/vision.md) para la definición de alcance, métricas de éxito, convenciones y política del catálogo de la Fase 0.

## Estructura del repositorio

- `catalog/`: catálogo de referencias normalizadas en YAML (datos, no código).
- `src/medidor/`: núcleo de visión, geometría, calibración, fusión, medidas y CLI en Python.
- `native/`: núcleo C++ (si se decide en la Fase 11).
- `app/`: aplicación Flutter (Android) + SQLite.
- `data/`: datasets (`raw/`, `annotated/`, `eval/`).
- `notebooks/`: experimentos y análisis de error.
- `tests/`: suite de tests (`pytest`).
- `docs/`: documentación técnica y de diseño.
- `scripts/`: utilidades y scripts auxiliares.
