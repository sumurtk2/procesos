# Mapa de Exposición a la IA de los Procesos Empresariales en España

Visualización interactiva de tipo treemap que muestra el grado de exposición a la inteligencia artificial de ~120 procesos empresariales habituales en empresas españolas.

## Características

- **120 procesos empresariales** organizados en 12 áreas funcionales
- **Doble vista**: PYME (10-50 empleados) y Gran Empresa (500+ empleados)
- **Puntuación dual**: exposición a la IA (0-10) y facilidad de implementación (0-10)
- **Treemap interactivo**: el tamaño de cada rectángulo representa el coste operativo relativo; el color, la exposición a la IA
- **Justificaciones en español**: cada proceso incluye una explicación detallada de su puntuación de exposición y de su facilidad de implementación

## Áreas funcionales

1. Administración General
2. Finanzas y Contabilidad
3. Recursos Humanos
4. Comercialización y Ventas
5. Marketing y Comunicación
6. Atención al Cliente
7. Logística y Cadena de Suministro
8. Producción y Operaciones
9. Tecnología e Informática
10. Legal y Cumplimiento
11. Investigación y Desarrollo
12. Dirección y Estrategia

## Estructura

```
docs/
├── index.html   # Aplicación web completa (HTML + CSS + JS)
└── data.json    # Datos de los 120 procesos con puntuaciones y justificaciones
```

## Uso

Abrir `docs/index.html` en un navegador web. Funciona como página estática sin necesidad de servidor (excepto para la carga del JSON, que requiere servir los archivos vía HTTP).

```bash
cd docs && python3 -m http.server 8000
```

Luego visitar `http://localhost:8000`.

## Metodología

- **Exposición a la IA (0-10)**: evalúa cuánto puede la IA transformar o automatizar el proceso con la tecnología actual y a corto plazo (2-3 años)
- **Facilidad de implementación (0-10)**: evalúa lo práctico que resulta implementar IA en ese proceso en una empresa española típica
- **Coste operativo**: porcentaje estimado del coste operativo total que representa cada proceso, diferenciando entre PYME y gran empresa
