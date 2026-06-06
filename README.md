# 📊 Tableros Interactivos

Colección de cinco proyectos web independientes desarrollados con fines educativos y demostrativos, cada uno orientado a un caso de negocio específico. Este repositorio muestra capacidades en visualización de datos, diseño de interfaces interactivas y toma de decisiones tecnológicas fundamentadas.

---

## 🚀 Tableros en vivo

| Proyecto | Acceso directo |
|---|---|
| ⚽ Fútbol Argentino | [▶ Ver tablero](https://coderhouse2025-droid.github.io/Tableros-Interactivos/F%C3%BAtbol%20Argentino/futbol_argentino.html) |
| 📊 Tablero de Control | [▶ Ver tablero](https://coderhouse2025-droid.github.io/Tableros-Interactivos/Tablero%20de%20Control/TC%20(6).html) |
| 👤 CV Dinámico | [▶ Ver tablero](https://coderhouse2025-droid.github.io/Tableros-Interactivos/Cv%20-%20Din%C3%A1mico/cv_dinamico_orellana.html) |
| 🛹 Dress Dashboard | [▶ Ver tablero](https://coderhouse2025-droid.github.io/Tableros-Interactivos/Dress/DRESS.html) |
| 📚 Librería Dashboard | [▶ Ver tablero](https://coderhouse2025-droid.github.io/Tableros-Interactivos/Librer%C3%ADa/dashboard.html) |

---

## 📁 Proyectos

### ⚽ Fútbol Argentino

**Caso de negocio:** Un medio deportivo o analista independiente necesita comunicar tendencias históricas del fútbol argentino de forma visual y accesible, sin requerir conocimientos técnicos del usuario final.

**Dataset y transformaciones:**
- Fuente: datos históricos de temporadas 2008–2022 (resultados, posiciones, goles).
- El dataset original presentaba inconsistencias en nombres de equipos (variantes tipográficas), fechas mal formateadas y registros duplicados por jornada.
- Se normalizaron los nombres de equipos, se unificó el formato de fechas a ISO 8601 y se eliminaron duplicados priorizando la fuente más reciente.
- Se calcularon métricas derivadas: promedio de goles por partido, diferencia de gol acumulada y racha de resultados.

**Decisiones tecnológicas:**
- **HTML/CSS/JavaScript vanilla** — se eligió sobre frameworks como React porque el tablero es de solo lectura, sin estado complejo ni componentes reutilizables. Reducir dependencias simplifica el despliegue en GitHub Pages sin proceso de build.
- **D3.js / Chart.js** — se prefirió sobre soluciones no-code (Tableau Desktop, Power BI) para mantener el control total del diseño visual y la portabilidad del proyecto en entorno web estático.

---

### 📊 Tablero de Control — Auditoría Presupuestaria

**Caso de negocio:** La Secretaría de Control Ecológico necesita un instrumento de rendición de cuentas que permita a auditores y funcionarios analizar la ejecución presupuestaria del ejercicio fiscal 2012, identificando desvíos por fuente de financiamiento y concepto de gasto.

**Dataset y transformaciones:**
- Fuente: datos del ejercicio fiscal 2012 (crédito original, modificaciones, devengado, pagado).
- El dataset original estaba en formato tabular plano sin jerarquía de programas. Se reestructuró en una jerarquía de tres niveles: fuente de financiamiento → programa → concepto de gasto.
- Se calcularon porcentajes de ejecución (devengado/crédito vigente) y se clasificaron los desvíos en rangos semafóricos (verde/amarillo/rojo) según umbrales definidos por la normativa de auditoría.
- Se incorporaron observaciones textuales vinculadas a cada partida con desvío significativo.

**Decisiones tecnológicas:**
- **React + Vite** — se eligió React por la necesidad de manejar estado complejo (filtros por fuente, por programa, por período) y renderizar condicionalmnete secciones de observaciones. Vite reduce el tiempo de build y genera un bundle optimizado para GitHub Pages.
- **Componentes controlados** — se optó por este patrón sobre soluciones de gestión de estado externo (Redux) dado que la complejidad del estado es media y no justifica la sobrecarga de una librería adicional.

---

### 👤 CV Dinámico

**Caso de negocio:** Un profesional de datos necesita una presentación personal diferenciadora que vaya más allá del PDF tradicional, permitiendo al reclutador explorar la experiencia de forma interactiva y con métricas visuales de competencias.

**Dataset y transformaciones:**
- Fuente: información biográfica y profesional estructurada manualmente en JSON.
- Se modeló la información en secciones independientes (experiencia, habilidades, educación, proyectos) con pesos numéricos para las barras de competencias.
- No requirió limpieza de datos, pero sí un proceso de jerarquización y priorización del contenido para guiar la lectura del reclutador.

**Decisiones tecnológicas:**
- **HTML/CSS con animaciones CSS** — se eligió sobre React para mantener el CV como un archivo autocontenido sin dependencias externas, lo que facilita compartirlo como URL directa o como archivo descargable.
- **Sin frameworks de UI** — se evitó Bootstrap/Tailwind para lograr un diseño completamente personalizado acorde a la identidad visual del profesional.

---

### 🛹 Dress Dashboard

**Caso de negocio:** Una tienda de indumentaria urbana y skate necesita monitorear en tiempo real las métricas clave de su negocio: ventas por categoría, stock disponible y tendencias de producto, para tomar decisiones de reposición y campaña.

**Dataset y transformaciones:**
- Fuente: datos de ventas e inventario estructurados para el período analizado.
- Se normalizaron las categorías de producto, se consolidaron variantes de talla/color en una misma referencia y se calcularon métricas de rotación de inventario.
- Se identificaron los productos de mayor y menor rotación para destacarlos en el tablero.

**Decisiones tecnológicas:**
- **HTML/CSS/JavaScript** — suficiente para un tablero de visualización estático con filtros básicos, sin necesidad de backend ni estado persistente.
- **Paleta visual oscura** — decisión de diseño orientada al público objetivo (cultura urbana/skate), coherente con la identidad de marca del caso de negocio.

---

### 📚 Librería Dashboard

**Caso de negocio:** Una librería independiente necesita un panel de gestión que le permita visualizar el desempeño de ventas por género literario, identificar los títulos más vendidos y detectar stock crítico, sin depender de un sistema ERP costoso.

**Dataset y transformaciones:**
- Fuente: datos de ventas por título, género y período.
- Se agruparon los registros por género literario y se calcularon participaciones porcentuales sobre el total de ventas.
- Se definieron umbrales de stock mínimo por categoría para activar alertas visuales.
- Se ordenaron los títulos por velocidad de rotación para generar el ranking de más vendidos.

**Decisiones tecnológicas:**
- **HTML/CSS/JavaScript** — la simplicidad del modelo de datos (sin relaciones complejas entre entidades) no justifica un framework. Un tablero estático bien construido cumple los requerimientos del caso a menor costo de mantenimiento.
- **Gráficos de torta y barras horizontales** — elegidos por ser los tipos de gráfico más intuitivos para el perfil del usuario final (dueño de librería sin formación técnica).

---

## 🧰 Tecnologías del repositorio

| Tecnología | Uso |
|---|---|
| HTML5 / CSS3 | Estructura y estilos en todos los proyectos |
| JavaScript (ES6+) | Lógica de interacción y manipulación de datos |
| React + Vite | Tablero de Control (estado complejo y componentes) |
| Chart.js / D3.js | Visualizaciones de datos |
| GitHub Pages | Despliegue estático sin costo |
| JSON | Estructura de datos para CV Dinámico |

---

## 📌 Objetivo del repositorio

Este repositorio funciona como portfolio técnico demostrando:

- Toma de decisiones tecnológicas fundamentadas en el caso de negocio
- Proceso completo de datos: desde dataset crudo hasta visualización final
- Capacidad de construir interfaces adaptadas al usuario final
- Organización modular y documentación metodológica de proyectos

---

*Desarrollado por [coderhouse2025-droid](https://github.com/coderhouse2025-droid)*
