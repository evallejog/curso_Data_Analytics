# Restaurant Analytics Lab - Week 2

**Autores:** Esteban Vallejo Galeano, Carlos Alberto Mancilla, Xavier Bravo

**Asignatura:** Data Analytics (Código: 43390860)  

**Semana:** 4 - Perfil del analista, modelo relacional y trabajo reproducible

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

## Informe Ejecutivo: Indicadores Clave

A partir del informe ejecutivo generado (`outputs/informe_ejecutivo.pdf`), se destacan los siguientes resultados:

| Indicador | Valor |
|---|---|
| Ingresos Semana 1 | $1,962.68 |
| Ingresos Semana 2 | $1,923.88 |
| Ingreso promedio por venta | $7.85 → $7.70 |
| Recurrencia de clientes (S1 → S2) | 20.8% |

### Frecuencia vs. Ingresos por Producto

| Producto | Frecuencia de compra | Ingresos |
|---|---|---|
| Drink | 1° lugar (más frecuente) | 8° lugar |
| Steak | 5° lugar | 1° lugar (más ingresos) |
| Burrito | 2° lugar | 3° lugar |

> El producto más comprado no es el que más ingresos genera: **Drink** lidera en frecuencia, pero **Steak** concentra los mayores ingresos gracias a su precio unitario.

### Hallazgos y Análisis

- Los ingresos cayeron de **$1,962.68** (semana 1) a **$1,923.88** (semana 2), con el mismo número de ventas (250 en cada semana); el ingreso promedio por registro bajó de $7.85 a $7.70.
- Sólo el **20.8%** de los clientes de la semana 1 (46 de 221) volvió a comprar en la semana 2; 175 clientes no regresaron y 178 fueron nuevos — el negocio depende más de atraer clientes nuevos que de retenerlos.
- Las ocupaciones con mayores ingresos agregados fueron *Compensation Analyst*, *Sales Representative* y *Marketing Manager*.

### Segmentación de Clientes (Recurrencia y Retención)

| Segmento | Clientes | % |
|---|---|---|
| Solo Semana 1 (Abandonos) | 175 | 43.9% |
| Nuevos (Solo Semana 2) | 178 | 44.6% |
| Recurrentes (Semana 1 y 2) | 46 | 11.5% |

---

## Proyecto Adicional: Estrategia de Prevención de Riesgos (CRISP-DM)

> **Nota:** Esta sección documenta un análisis independiente, correspondiente a otro dataset (trabajadores, empresas y accidentes laborales) bajo el marco metodológico CRISP-DM. Se incluye aquí como referencia adicional del curso, pero no forma parte del pipeline de datos de la cadena de restaurantes descrito arriba.

### Mapeo Metodológico

En la fase de **Data Understanding** se cargaron y perfilaron tres fuentes disponibles (`trabajadores.csv`, `empresas.csv`, `accidentes.csv`), identificando sus llaves de relación y calidad de datos. En **Data Preparation** se ejecutó un triple join: primero un merge interno entre trabajadores y empresas, y luego un left join con accidentes — decisión clave para conservar en la tabla maestra a los trabajadores sin incidentes y así calcular tasas reales de accidentalidad sobre **3,000 registros consolidados**. Se derivó la variable binaria `incidente` como eje del análisis descriptivo.

### Diagnóstico de Factores de Riesgo

**Jornada:** La jornada nocturna presenta la mayor accidentalidad, con una tasa de **45.0%**, seguida de la jornada mixta (34.5%) y la diurna (32.2%).

**Capacitación:** Contrario a lo esperado, los trabajadores capacitados presentan una tasa de incidentes de **41.7%**, superior a la de los no capacitados (31.0%), con correlación positiva débil (r = 0.11). Esto no implica que la capacitación cause accidentes: refleja más bien sesgo de asignación (el personal capacitado suele ubicarse en cargos o sectores de mayor exposición) o sesgo de reporte (mayor conciencia y registro de incidentes menores).

### Hallazgos Adicionales

1. **Sistema de Gestión:** El factor con mayor poder explicativo del análisis. Empresas sin sistema de gestión formal registran **57.6%** de incidentes (n=505), frente a **31.1%** en las que sí lo tienen (n=2,495) — correlación más fuerte del dataset (r = -0.21), equivalente a 26.5 puntos porcentuales de reducción.
2. **Antigüedad:** Sin patrón relevante. Las tasas oscilan entre 35% y 40% en todos los rangos, con correlación prácticamente nula (r = -0.01). No es un predictor útil de riesgo.
3. **Nivel Educativo:** Tasas relativamente homogéneas (23%-30%), sin diferencias estadísticamente contundentes entre niveles; no se recomienda como criterio de priorización.
4. **Interacción Capacitación con Sistema de Gestión:** Incluso dentro de empresas con sistema de gestión, los trabajadores capacitados muestran mayor tasa de incidentes que los no capacitados, reforzando que el efecto de capacitación responde a sesgo de asignación a roles de riesgo y no al sistema de gestión en sí.

### Recomendación ERP (Insight Accionable)

Los resultados muestran que el sistema de gestión presenta el mayor efecto protector (-26.5 p.p.), por lo que se propone **bloquear en el ERP la activación de nuevas empresas o sedes** hasta certificar un sistema de gestión de riesgo laboral vigente, además de generar **alertas trimestrales** para las que aún no lo tengan. También se recomienda analizar los incidentes según antigüedad, nivel educativo y capacitación, evitando usar "capacitado = Sí" como indicador aislado.

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