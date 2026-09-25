# Calculadora de Corte PVC/PPR

Herramienta web interactiva para calcular el largo real de corte de tuberías considerando accesorios (codos, tees) y generar planos de corte visuales.

## Descripción

Esta aplicación permite a ingenieros y instaladores calcular rápidamente el tubo a cortar considerando las distancias de eje a eje y los descuentos por accesorios. Incluye un visualizador CAD responsivo y un gestor de perfiles de tuberías para guardar configuraciones personalizadas.

## Características Principales

- **Cálculo de corte eje a eje**: Introduce la distancia total y los accesorios en cada extremo para obtener el largo real de corte
- **Visualizador CAD interactivo**: Plano generado en SVG que se adapta a cualquier pantalla, con leyenda de colores explicativa
- **Gestor de perfiles de tuberías**: Guarda y recupera configuraciones personalizadas de accesorios (codos, tees laterales y centrales)
- **Diseño responsive**: Funciona en dispositivos móviles y de escritorio
- **Cálculo en tiempo real**: Actualizaciones instantáneas mientras introduces los parámetros

## Tecnologías Utilizadas

- **HTML5**: Estructura semántica y accesible
- **CSS3**: Variables personalizadas, Flexbox, Grid y animaciones
- **JavaScript Vanilla**: Lógica de cálculo y manipulación DOM sin dependencias externas
- **SVG**: Generación de gráficos vectoriales responsivos

## Uso

### Calculadora de Corte

1. Selecciona una tubería guardada en el menú desplegable o deja "Ninguna" para valores personalizados
2. Introduce la distancia total eje a eje en milímetros
3. Selecciona el accesorio del extremo izquierdo y derecho (o "Nada" si es el final de tubo)
4. Haz clic en **"Generar Plano de Corte"** para ver el resultado

### Gestor de Tuberías

1. Ve a la pestaña **"Gestor de Tuberías"**
2. Introduce un nombre para la tubería (ej: "SCH 80 2"")
3. Configura las medidas de cada accesorio:
   - **Codo**: Eje a borde y fondo a borde
   - **Tee (Lados)**: Eje a borde y fondo a borde
   - **Tee (Centro)**: Eje a borde y fondo a borde
4. Haz clic en **"Guardar / Actualizar Medidas"**

## Estructura del Proyecto

```
calculadora_medidas_pvc_ppr/
├── index.html          # Archivo principal (estructura, estilo y lógica)
```

*Nota: Todo el proyecto está contenido en un solo archivo HTML por simplicidad y portabilidad. Las variables CSS, la lógica JavaScript y la estructura HTML están integradas.*

## Colores del Visualizador CAD

El plano utiliza un sistema de codificación por colores:

| Color | Variable CSS | Representación |
|-------|-------------|----------------|
| Celeste | `--cad-line` | Pieza/tubo general |
| Rosa | `--cad-axis` | Distancia Ejes (medida total) |
| Ámbar | `--cad-eje-borde` | Medida Eje a Borde (dentro del accesorio) |
| Verde | `--cad-corte` | Largo del tubo a cortar |
| Rosado | `--cad-perdida` | Distancia perdida en el fondo |

## Funcionalidades Avanzadas

- **Cálculo preciso**: `corte_real = distancia_total - descuento_accesorio_1 - descuento_accesorio_2`
- **Validación de errores**: Alerta si los accesorios descuentan más de la distancia total
- **Persistencia local**: Las configuraciones de tuberías se guardan en `localStorage`
- **Diseño responsivo**: Se adapta desde pantallas pequeñas (480px) hasta escritorio

## Posibles Mejoras Futuras

- Import/export de configuraciones de tuberías
- Biblioteca de accesorios predefinidos por norma/standar
- Generación de reporte PDF
- Integración con bases de datos de materiales
- Modo oscuro/claro automático

## Autor

Desarrollado como herramienta de cálculo para trabajos de instalaciones.