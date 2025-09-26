# Sistema de Gestión de Inventarios

Un sistema completo para gestionar el inventario de una tienda desarrollado en Python. Permite agregar, actualizar, buscar productos y generar reportes detallados.

## Características Principales

### Gestión de Productos
- **Agregar productos**: Cada producto incluye ID, nombre, categoría, precio, cantidad en stock y fecha de última actualización
- **Eliminar productos**: Eliminación segura con confirmación
- **Actualizar stock**: Modificar cantidades en inventario
- **Actualizar precios**: Cambiar precios de productos existentes

### Búsqueda y Consultas
- **Búsqueda por nombre**: Búsqueda parcial e insensible a mayúsculas
- **Búsqueda por categoría**: Filtrar productos por categoría
- **Mostrar todos los productos**: Lista completa del inventario

### Reportes y Estadísticas
- **Reporte de stock bajo**: Productos con cantidad menor a un umbral configurable
- **Valor total del inventario**: Cálculo del valor total (precio × cantidad)
- **Estadísticas completas**:
  - Producto más caro y más barato
  - Promedio de precios por categoría
  - Total de productos y valor del inventario

### Persistencia de Datos
- **Guardado automático**: Los datos se guardan automáticamente en formato JSON
- **Carga automática**: Los datos se cargan al iniciar la aplicación
- **Archivo de datos**: `inventario.json` (se crea automáticamente)

## Requisitos del Sistema

- Python 3.6 o superior
- No se requieren dependencias externas (utiliza solo la biblioteca estándar)

## Instalación y Uso

1. **Clonar o descargar el proyecto**
   ```bash
   # Si tienes git instalado
   git clone <url-del-repositorio>
   cd gestion-de-inventarios-en-python
   ```

2. **Ejecutar la aplicación**
   ```bash
   python main.py
   ```

3. **Usar el menú interactivo**
   - Selecciona las opciones del menú principal
   - Sigue las instrucciones en pantalla
   - Los datos se guardan automáticamente

## Estructura del Proyecto

```
gestion-de-inventarios-en-python/
├── main.py              # Aplicación principal con interfaz de usuario
├── producto.py          # Clase Producto
├── inventario.py        # Clase Inventario con lógica de negocio
├── inventario.json      # Archivo de datos (se crea automáticamente)
├── requirements.txt     # Requisitos del proyecto
└── README.md           # Este archivo
```

## Funcionalidades Detalladas

### 1. Gestión de Productos

#### Agregar Producto
- ID único del producto
- Nombre descriptivo
- Categoría de clasificación
- Precio (no negativo)
- Cantidad en stock (no negativa)
- Fecha de última actualización (automática)

#### Operaciones CRUD
- **Create**: Agregar nuevos productos
- **Read**: Buscar y mostrar productos
- **Update**: Actualizar stock y precios
- **Delete**: Eliminar productos (con confirmación)

### 2. Sistema de Búsqueda

#### Búsqueda por Nombre
- Búsqueda parcial (encuentra productos que contengan el texto)
- Insensible a mayúsculas y minúsculas
- Muestra todos los productos que coincidan

#### Búsqueda por Categoría
- Filtrado por categoría específica
- Búsqueda parcial en nombres de categoría
- Lista todos los productos de la categoría

### 3. Reportes y Análisis

#### Reporte de Stock Bajo
- Identifica productos con stock menor al umbral configurable
- Umbral por defecto: 10 unidades
- Configurable desde el menú principal

#### Valor del Inventario
- Cálculo automático del valor total
- Suma de (precio × cantidad) para todos los productos
- Reporte detallado con estadísticas

#### Estadísticas Avanzadas
- **Producto más caro**: Identifica el producto con mayor precio
- **Producto más barato**: Identifica el producto con menor precio
- **Promedio por categoría**: Calcula el precio promedio de cada categoría
- **Resumen general**: Total de productos y valor del inventario

### 4. Persistencia de Datos

#### Formato JSON
- Datos estructurados en formato JSON legible
- Fácil de respaldar y migrar
- Compatible con otros sistemas

#### Operaciones Automáticas
- **Guardado**: Automático después de cada modificación
- **Carga**: Automática al iniciar la aplicación
- **Manejo de errores**: Recuperación automática de errores de archivo

## Ejemplos de Uso

### Agregar Productos
1. Selecciona opción "1. Agregar producto"
2. Ingresa los datos del producto:
   - ID: "PROD001"
   - Nombre: "Laptop Dell"
   - Categoría: "Electrónicos"
   - Precio: 899.99
   - Cantidad: 5

### Buscar Productos
1. Selecciona "5. Buscar producto por nombre"
2. Ingresa "laptop" para encontrar todos los productos que contengan esa palabra

### Generar Reportes
1. Selecciona "8. Reporte de productos bajo stock"
2. El sistema mostrará todos los productos con stock menor al umbral configurado

## Características Técnicas

### Arquitectura
- **Separación de responsabilidades**: Lógica de negocio separada de la interfaz
- **Clases bien definidas**: Producto e Inventario con responsabilidades claras
- **Manejo de errores**: Validación de entrada y manejo de excepciones

### Validaciones
- **Datos de entrada**: Validación de tipos y rangos
- **ID únicos**: Prevención de duplicados
- **Valores negativos**: Prevención de precios y cantidades negativas
- **Confirmaciones**: Para operaciones destructivas

### Interfaz de Usuario
- **Menú intuitivo**: Navegación clara y fácil
- **Mensajes informativos**: Feedback claro para el usuario
- **Manejo de errores**: Mensajes de error descriptivos
- **Limpieza de pantalla**: Interfaz limpia y organizada

## Extensibilidad

El sistema está diseñado para ser fácilmente extensible:

- **Nuevas funcionalidades**: Agregar métodos a las clases existentes
- **Nuevos reportes**: Implementar métodos en la clase Inventario
- **Nuevas validaciones**: Extender las validaciones existentes
- **Nuevos formatos**: Agregar soporte para otros formatos de datos

## Solución de Problemas

### Error al cargar datos
- Verifica que el archivo `inventario.json` no esté corrupto
- Si hay problemas, elimina el archivo para empezar de nuevo

### Producto no encontrado
- Verifica que el ID del producto sea correcto
- Usa la búsqueda para encontrar productos por nombre

### Error de permisos
- Asegúrate de tener permisos de escritura en el directorio
- Verifica que no haya otro proceso usando el archivo de datos

## Contribuciones

Para contribuir al proyecto:

1. Haz un fork del repositorio
2. Crea una rama para tu funcionalidad
3. Implementa los cambios
4. Prueba exhaustivamente
5. Envía un pull request
