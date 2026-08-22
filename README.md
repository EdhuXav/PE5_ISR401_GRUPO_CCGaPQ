# PE5 — Integración, Métricas y Defensa del Proyecto Integrador de IR

**Universidad Técnica Estatal de Quevedo (UTEQ)**  
**Facultad de Ciencias de la Computación y Diseño Digital**  
**Carrera de Ingeniería de Software (Rediseño)**

---

## Datos de identificación

| Campo | Detalle |
|---|---|
| **Asignatura** | Ingeniería de Requerimientos \[20303\] — ISR-401 |
| **Práctica** | PE5: Integración, Métricas y Defensa del Proyecto Integrador |
| **Sistema (PFC)** | CarniCore — Sistema de Trazabilidad, Pesaje Inteligente e Inventario para Distribuidora de Cárnicos Pucayacu, La Maná, Cotopaxi |
| **Curso** | 4.º «A» Software |
| **Docente** | PhD. Guerrero Ulloa Gleiston Cicerón |
| **Periodo** | 2026-2027 PPA |
| **Fecha de entrega** | 21 de agosto de 2026 |

---

## Integrantes

| Nombre | Cédula | Rol en la inspección Fagan |
|---|---|---|
| Castro Bajaña Ariel Omar | 2350262305 | Moderador |
| Crespo Espinoza Kleber Obed | 1315380244 | Lector |
| Gamarra Araujo Edhu Xavier | 1208370633 | Inspector 1 (perspectiva de negocio) |
| Pérez Ruiz Carlos Andrés | 0955713136 | Inspector 2 (perspectiva técnica) |
| Quintero Gende Erick Jahir | 1250575527 | Inspector 3 (perspectiva normativa) |

---

## Repositorio

```
https://github.com/EdhuXav/PE5_ISR401_GRUPO_CCGaPQ
```

---

## Estructura del repositorio

```
PE5_ISR401_GRUPO_CCGaPQ/
│
├── informe/
│   ├── figuras/                                              ← Diagramas UML, mockups y capturas
│   ├── PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex   ← Archivo principal LaTeX
│   ├── referencias.bib                                       ← Bibliografía BibTeX (IEEE style)
│   └── .gitkeep
│
├── trazabilidad/
│   ├── matriz_trazabilidad.csv    ← 60 filas: 42 base (27 RF + 15 RNF) + 18 IA (cadena end-to-end)
│   └── backlog_trello.csv         ← Historias de usuario HU-01 a HU-27 exportadas desde Trello
│
├── defensa/
│   ├── CarniCore_PE5_Defensa.pptx          ← Presentación para el tribunal
│   ├── banco_preguntas_respuestas.pdf       ← 10 preguntas con respuestas ancladas en artefactos
│   └── .gitkeep
│
├── metricas_IA/
│   └── auditoria_calidad_M1_M6.xlsx        ← Métricas M1–M6 con conteos auditables y par antes/después
│
└── README.md
```

---

## Instrucciones de compilación (criterio G2)

### Requisitos previos

| Herramienta | Versión mínima | Instalación |
|---|---|---|
| TeX Live | 2022+ | `sudo apt install texlive-full` (Ubuntu/Debian) |
| pdfLaTeX | incluido en TeX Live | — |
| BibTeX | incluido en TeX Live | — |
| latexmk *(opcional)* | incluido en TeX Live | — |

### Pasos para compilar

**Opción A — comandos manuales (4 pasadas):**

```bash
# 1. Clonar el repositorio
git clone https://github.com/EdhuXav/PE5_ISR401_GRUPO_CCGaPQ.git
cd PE5_ISR401_GRUPO_CCGaPQ/informe

# 2. Primera pasada pdfLaTeX
pdflatex PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex

# 3. Procesar bibliografía
bibtex PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ

# 4. Segunda y tercera pasadas para referencias cruzadas e índices
pdflatex PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex
pdflatex PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex
```

**Opción B — latexmk (recomendado, una sola línea):**

```bash
cd PE5_ISR401_GRUPO_CCGaPQ/informe
latexmk -pdf -bibtex PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex
```

### Resultado esperado

El archivo `informe/PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.pdf` se genera con **≥ 40 páginas de contenido**.

Si la compilación falla por paquetes faltantes, instalar con:

```bash
tlmgr install booktabs longtable colortbl multirow tabularx subcaption tocloft
```

---

## Tablero de gestión Trello

El *product backlog* del proyecto (historias de usuario HU-01 a HU-27, épicas EPIC-01 a EPIC-05, RFC y defectos Fagan) se gestionó en:

```
https://trello.com/b/CCGaPQ/carnicore-pe5
```

---

## Línea base y etiquetas Git

| Etiqueta | Versión ERS | PE | Descripción |
|---|---|---|---|
| `v1.0-PE1` | v1.0 | PE1 | ERS inicial con 10 RF preliminares |
| `v2.0-PE2` | v2.0 | PE2 | ERS con 15 RF, 6 RNF y mockups de baja fidelidad |
| `baseline-v1.1` | v3.0 | PE3/PE4 | Línea base aprobada — 25 RF, 15 RNF, Fagan, CCB |
| `v4.0-final` | v4.0 | PE5 | Versión de cierre — RF-26, RF-27, IA, métricas |

Para verificar los tags localmente:

```bash
git clone https://github.com/EdhuXav/PE5_ISR401_GRUPO_CCGaPQ.git
cd PE5_ISR401_GRUPO_CCGaPQ
git tag -l
git show baseline-v1.1
```

---

## Resumen de artefactos entregados

| Artefacto | Ubicación en el repositorio | Descripción |
|---|---|---|
| Informe final (fuente LaTeX) | `informe/PE5_U5_PFC_FINAL_CASTRO_CRESPO_GAMARRA_QUINTERO_PEREZ.tex` | Fuente LaTeX del informe ≥ 40 págs. |
| ERS/SRS v4.0 | Sección 3 del informe | 27 RF + 15 RNF, versionado en Git |
| Matriz de trazabilidad | `trazabilidad/matriz_trazabilidad.csv` | 60 filas, cadena Fuente → RF → CU → Clase → Estado → BDD → CP → HU |
| Backlog Trello | `trazabilidad/backlog_trello.csv` | HU-01 a HU-27 con criterios Gherkin y estado |
| Requisitos de IA | Sección 7 del informe | IA-01 (predictor de demanda) e IA-02 (detector cadena de frío) |
| Auditoría de calidad | `metricas_IA/auditoria_calidad_M1_M6.xlsx` | M1–M6 con conteos auditables y par antes/después |
| Presentación defensa | `defensa/CarniCore_PE5_Defensa.pptx` | Diapositivas para el tribunal |
| Banco de preguntas | `defensa/banco_preguntas_respuestas.pdf` | 10 preguntas con respuestas ancladas en artefactos |

---

## Métricas de calidad alcanzadas (ERS v4.0)

| Métrica | Antes (v3.0) | Después (v4.0) | Umbral | Cumple |
|---|---:|---:|---|:---:|
| M1a — Completitud de atributos | 95,0 % | 97,5 % | ≥ 95 % | ✓ |
| M2 — Consistencia | 0,9987 | 1,0000 | ≥ 0,98 | ✓ |
| M3 — Verificabilidad | 92,5 % | 97,5 % | ≥ 90 % | ✓ |
| M4ade — Trazabilidad adelante | 92,0 % | 96,0 % | ≥ 90 % | ✓ |
| M4atr — Trazabilidad hacia atrás | 100,0 % | 100,0 % | 100 % | ✓ |
| M5 — Modificabilidad | 2,71 req | 2,71 req | ≤ 3,0 | ✓ |
| M6 — Corrección | 0,10 def/req | 0,00 def/req | ≤ 0,05 | ✓ |

---

## Declaración de uso de inteligencia artificial

El equipo utilizó Claude (Anthropic) y ChatGPT (OpenAI) como apoyo en corrección de estilo, ortografía y formato de tablas LaTeX. Todo el contenido evaluativo — análisis, justificaciones de decisiones de ingeniería, conclusiones y métricas — fue producido y validado íntegramente por el equipo. Los conteos que respaldan las métricas fueron realizados manualmente y verificados de forma independiente por al menos dos integrantes. El detalle completo se encuentra en el Anexo D del informe.

---

*Documento de uso académico — Ingeniería de Requisitos (ISR-401) — UTEQ, 2026-2027 PPA.*
