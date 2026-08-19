# Restaurant Analytics Lab - Week 2

**Autores:** Esteban Vallejo Galeano, Carlos Alberto Mancilla, Xavier Bravo

**Asignatura:** Data Analytics (Código: 43390860)  
**Semana:** 2 - Perfil del analista, modelo relacional y trabajo reproducible

---

## Descripción del Proyecto

Este proyecto consiste en un análisis de datos integral de una cadena de restaurantes. Se consolidan datos dispersos en cuatro archivos independientes (productos, clientes y ventas de dos semanas) para generar indicadores clave que apoyen decisiones sobre el menú y estrategias de fidelización.

### Contexto de Negocio

La cadena de restaurantes dispone de datos de:
- **Productos:** Catálogo de alimentos y bebidas
- **Clientes:** Base de datos de clientela
- **Ventas (Semana 1 y 2):** Transacciones de ambas semanas

**Desafío:** La gerencia conoce cuánto vende, pero no puede:
- Comparar desempeño entre semanas
- Identificar productos de mayor generación de ingresos
- Estimar la recurrencia de clientes

**Objetivo:** Construir indicadores que apoyen decisiones estratégicas sobre menú y fidelización.

---

## Alcance del Análisis

El análisis se enfoca en:
- **Consolidación de fuentes:** Unión e integración de datos relacionales
- **Validación de datos:** Verificación de integridad referencial
- **Indicadores clave:**
  - Desempeño de productos (productos más vendidos, ingresos por categoría)
  - Comparativas semanales (crecimiento/decrecimiento de ventas)
  - Recurrencia de clientes (frecuencia de compra, clientes recurrentes)

**Nota:** Los archivos contienen precios de venta, pero no costos ni descuentos. El análisis se enfoca en ingresos y frecuencia, no en rentabilidad ni margen.

---

## Estructura del Proyecto

```
lab-restaurant/
├── data/
│   ├── Restaurant-Foods.csv              # Catálogo de productos
│   ├── Restaurant-Customers.csv          # Base de clientes
│   ├── Restaurant-Week1-Sales.csv        # Ventas semana 1
│   ├── Restaurant-Week2-Sales.csv        # Ventas semana 2
│   └── lab_Sem2_DA_20261.ipynb          # Notebook del análisis
├── README.md                             # Este archivo
└── outputs/
    └── informe_ejecutivo.pdf             # Reporte de una página
```

---

## 🛠️ Requisitos y Dependencias

### Versiones Recomendadas
- Python 3.8+
- pandas 1.3+
- numpy 1.20+
- jupyter 1.0+
- matplotlib 3.3+

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/lab-restaurant.git
cd lab-restaurant

# Crear entorno virtual (opcional pero recomendado)
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt
```

---

## Cómo Usar

### 1. Preparar el ambiente
```bash
cd lab-restaurant
jupyter notebook
```

### 2. Ejecutar el análisis
Abrir y ejecutar `data/lab_Sem2_DA_20261.ipynb` celda por celda.

### 3. Generar outputs
El notebook genera automáticamente:
- Tablas consolidadas
- Visualizaciones comparativas
- Indicadores de recurrencia
- Reportes en formato tabla

---

## Resultados Principales

El análisis incluye:

1. **Análisis de Productos**
   - Top productos por ingresos
   - Distribución de ventas por categoría
   - Variabilidad entre semanas

2. **Comparativa Semanal**
   - Ingresos totales semana 1 vs semana 2
   - Cambios en preferencias de clientes
   - Tendencias de consumo

3. **Recurrencia de Clientes**
   - Clientes presentes en ambas semanas
   - Frecuencia de compra por cliente
   - Segmentación de lealtad

---

## Deliverables

- Notebook Jupyter con análisis reproducible
- Dataset consolidado (relaciones validadas)
- Informe ejecutivo de una página
- Visualizaciones en formato PDF/PNG

---

## Modelo Relacional

El proyecto implementa un modelo relacional simple:

```
Restaurant-Foods (ID_Producto, Nombre, Categoría, Precio)
    │
    ├─── Semana 1 (ID_Transacción, ID_Producto, ID_Cliente, Fecha, Monto)
    │
    ├─── Semana 2 (ID_Transacción, ID_Producto, ID_Cliente, Fecha, Monto)
    │
Restaurant-Customers (ID_Cliente, Nombre, Email, Ciudad)
```

---

## Buenas Prácticas Implementadas

- Código reproducible y documentado
- Manejo de datos relacionales validado
- Visualizaciones claras y profesionales
- Comentarios explicativos en el código
- Separación de datos (inputs) y resultados (outputs)
- Documentación en archivo README

---

## Contacto

Para preguntas o sugerencias sobre este proyecto, contactar a cualquiera de los autores:
- **Esteban Vallejo Galeano**
- **Carlos Alberto Mancilla**
- **Xavier Bravo**

---

## Licencia

Este proyecto es parte de la asignatura Data Analytics de la Universidad Central.

---

**Última actualización:** Agosto 2026
