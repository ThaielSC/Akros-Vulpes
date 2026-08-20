# Guía de Identidad y Estilo de Marca: Akros Vulpes

Esta guía de marca establece la dirección visual, la paleta de colores y las directrices de diseño para la plataforma web del equipo de Formula SAE de la Universidad de los Andes (Chile).

---

## 1. Identidad y Concepto

El nombre **Akros Vulpes** unifica dos ideas clave:
1. **Akros** (griego: "altura", "cumbre"): Representa la imponente cordillera de los Andes que rodea a Santiago y la búsqueda de la excelencia en ingeniería.
2. **Vulpes** (latín: "zorro"): Hace referencia al **Zorro Culpeo**, un cánido nativo de la cordillera, ágil, rápido e inteligente, cualidades esenciales para el monoplaza de competición y el equipo.

El tono de la comunicación visual debe ser **técnico, académico, pero fuertemente deportivo y agresivo**, inspirado en la estética de la Formula 1 moderna y la ingeniería de competición.

---

## 2. Paleta de Colores

La paleta evoca la tierra de la cordillera, el pelaje del zorro culpeo y la elegancia de los materiales compuestos de competición (fibra de carbono, titanio).

| Color | Hex | Uso Recomendado |
| :--- | :--- | :--- |
| **Negro** | `#0A0A0A` | Fondo principal, secciones de alta tensión. |
| **Carbón** | `#1E1E1A` | Tarjetas, contenedores, y fondos secundarios. Simula la textura de fibra de carbono. |
| **Gris Andino** | `#8A8A82` | Bordes técnicos, líneas de cuadrícula y textos secundarios. |
| **Oro Andino** | `#B8966A` | Acentos premium, insignias de victoria, logos destacados y detalles mecánicos. |
| **Terracota** | `#C1522A` | Elementos interactivos secundarios, degradados de temperatura del motor. |
| **Rojo Culpeo** | `#8B3A1F` | Acento principal de velocidad, alertas, estados de hover e indicador de peligro. |
| **Blanco Hueso** | `#F5F2EE` | Texto de lectura principal, títulos de alto contraste. |

---

## 3. Tipografía

Utilizaremos fuentes de Google Fonts para reflejar tanto la fuerza del deporte como la precisión de la ingeniería.

*   **Títulos Principales (Headings):** **Outfit** (Peso: 800 / 900)
    *   *Estilo:* Negrita extrema, frecuentemente en mayúsculas y con inclinación cursiva (`font-style: italic`) para simular velocidad.
*   **Datos Técnicos y Monitoreo:** **Space Mono** (Peso: 400 / 700)
    *   *Estilo:* Monoespaciada, limpia. Se utiliza para telemetría, especificaciones del auto, números y etiquetas de fases.
*   **Cuerpo de Texto:** **Inter** o **Plus Jakarta Sans** (Peso: 400 / 500 / 600)
    *   *Estilo:* Sans-serif geométrica altamente legible.

---

## 4. Elementos de Diseño e Inspiración F1

Para lograr una apariencia premium y agresiva que no luzca genérica, utilizaremos los siguientes recursos visuales:

### A. Líneas Inclinadas (Slanted / Speedlines)
El dinamismo se genera rompiendo la horizontalidad. Utiliza `skewX(-8deg)` en botones y contenedores destacados.
```css
.btn-racing {
  transform: skewX(-8deg);
  background-color: var(--color-rojo-culpeo);
  color: var(--color-blanco-hueso);
  font-family: 'Outfit', sans-serif;
  text-transform: uppercase;
}
```

### B. Cuadrícula de Ingeniería (Blueprint Grid)
Uso de fondos con patrones de cuadrícula técnica en marcas de agua para dar un aspecto académico y de diseño industrial.
```css
.blueprint-bg {
  background-image: 
    radial-gradient(var(--color-gris-andino) 1px, transparent 1px),
    linear-gradient(to right, rgba(138, 138, 130, 0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(138, 138, 130, 0.05) 1px, transparent 1px);
  background-size: 24px 24px;
}
```

### C. Bordes Biselados y Marcos Técnicos
Evitar los bordes redondeados tradicionales en elementos principales. Usar esquinas cortadas (`clip-path`) para simular paneles del chasis del monoplaza.
```css
.bevel-card {
  clip-path: polygon(0 0, 100% 0, 100% calc(100% - 15px), calc(100% - 15px) 100%, 0 100%);
  border: 1px solid var(--color-gris-andino);
}
```

### D. Micro-Interacciones
- **Hover en botones:** El texto se desplaza ligeramente y el fondo cambia usando un degradado de `Terracota` a `Rojo Culpeo`.
- **Efecto Scanner:** Un reflejo de luz que pasa de izquierda a derecha en las tarjetas principales al hacer hover.
- **Parallax y Scrollytelling:** El fondo de la página se desplaza a una velocidad diferente al contenido para dar profundidad tridimensional (3D depth) mientras se recorre el auto.
