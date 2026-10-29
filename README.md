# 2do Proyecto: Visualización Reproducible en Python (Seaborn y Plotly)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Juliand10x/Proyecto-2---visualizaci-n/blob/main/Equipo_Duarte_Jimenez_Proyecto2_Visualizacion.ipynb)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Repositorio_Oficial-1B365D?logo=github)](https://github.com/Juliand10x/Proyecto-2---visualizaci-n)
[![Vercel Live](https://img.shields.io/badge/Vercel-Despliegue_En_Vivo-black?logo=vercel)](https://visualizacion-proyecto-2.vercel.app)

**Curso:** Visualización 1 — Universidad Externado de Colombia  
**Integrantes:** Julián Steven Duarte y Julián Camilo Jiménez  
**Docente:** Luz Adriana Pineda Barón  
**Fuente de Datos Oficial:** *World Happiness Report 2024* (`WHR24_Data_Figure_2.1.xls`)  

---

## 🎯 1. Encuadre Estratégico, Audiencia y Pregunta Analítica

* **Audiencia Técnica:** Comisión Técnica de Evaluación de Políticas de Bienestar de Organismos Multilaterales de Cooperación y Desarrollo (ej. PNUD / OCDE / BID).
* **Pregunta Analítica Central:**  
  > *¿Cómo se diferencian los perfiles de bienestar entre las macro-regiones del mundo y en qué medida los factores relacionales e institucionales (soporte social, libertad individual y percepción de corrupción) explican la resiliencia en países de ingreso medio frente a aquellos estancados en trampas de bajo bienestar subjetivo?*

---

## 📁 2. Estructura y Organización del Repositorio

El proyecto cumple con los 5 entregables y la convención oficial exigida por la rúbrica:

```text
├── Equipo_Duarte_Jimenez_Proyecto2_Entregables.zip           # Paquete consolidado listo para entrega
├── Equipo_Duarte_Jimenez_Proyecto2_Documento_Ejecutivo.pdf   # Entregable 3 y 5: Informe Ejecutivo (3 págs.) + Anexo IA (1 pág.)
├── Equipo_Duarte_Jimenez_Proyecto2_Documento_Ejecutivo.tex   # Código fuente en LaTeX compilado con pdflatex
├── Equipo_Duarte_Jimenez_Proyecto2_Visualizacion.ipynb       # Entregable 1: Notebook Jupyter completamente ejecutado y reproducible
├── Equipo_Duarte_Jimenez_Proyecto2_Visualizaciones_Interactivas.html # Entregable 2: Reporte interactivo Plotly autocontenido (4.9 MB)
├── NOTAS_ENTREGA_Y_ENLACES.txt                               # Acceso directo a Vercel, Google Colab y GitHub
├── Datos_Proyecto/                                           # Entregable 4: Datos oficiales
│   └── WHR24_Data_Figure_2.1.xls                             # Archivo fuente original del World Happiness Report 2024
├── figuras/                                                  # Figuras estáticas en alta resolución (300 DPI)
│   ├── fig1_distribucion_regional.png                        # Seaborn: Distribución y asimetría del bienestar por macro-región
│   ├── fig2_matriz_correlaciones.png                         # Seaborn: Matriz de correlaciones lineales de los pilares de bienestar
│   ├── fig3_paradoja_desarrollo.png                          # Seaborn: Riqueza (PIB) vs Soporte Social (Dividendo Relacional)
│   └── fig4_brecha_institucional.png                         # Seaborn: Brecha institucional entre cuartiles extremos (Q1 vs Q4)
├── Documentos/                                               # Guías y especificaciones de la asignatura
│   ├── Instrucciones_Proyecto_2_Visualizacion_Python.pdf     # Pautas oficiales, rúbrica (50 pts) y criterios de entrega
│   └── Visualización I - microcurrículo.pdf                  # Programa académico
├── Materiales_de_apoyo/                                      # Notebooks de clase (Seaborn I-II, Plotly I-II)
└── README.md                                                 # Documentación global del repositorio
```

---

## 📊 3. Visualizaciones Desarrolladas

### Visualizaciones Estáticas (Seaborn)
1. **Distribución del Bienestar Global por Región (`fig1_distribucion_regional.png`):** Boxplot y jitter points ordenados por la mediana regional. Revela la polarización entre el bloque occidental ($6.84 - 6.93$) y regiones de alta vulnerabilidad ($\sim 4.14 - 4.38$).
2. **Arquitectura de Correlaciones (`fig2_matriz_correlaciones.png`):** Matriz triangular de coeficientes Pearson. Demuestra que el **Soporte Social** ($r = 0.81$) presenta mayor correlación con la satisfacción de vida que el PIB per cápita ($r = 0.77$) y la longevidad ($r = 0.76$).
3. **La Paradoja del Desarrollo (`fig3_paradoja_desarrollo.png`):** Gráfico de dispersión con ajuste de regresión OLS entre PIB y Soporte Social. Evidencia el *dividendo relacional* de América Latina, cuyos países se sitúan sistemáticamente por encima de la línea global.
4. **La Brecha Institucional (`fig4_brecha_institucional.png`):** Comparación cuantitativa entre el cuartil superior ($Q4$) y el inferior ($Q1$). La transparencia institucional es **3.7 veces superior** en los países más felices ($0.279$ vs. $0.076$), mientras la libertad cívica es $62\%$ mayor.

### Visualizaciones Interactivas (Plotly)
1. **Explorador Multidimensional de Bienestar:** Gráfico de burbujas interactivo que integra PIB (X), Salud (Y), Soporte Social (tamaño) y Macro-región (color) con aislamiento dinámico de trazas e inspección detallada por país.
2. **Descomposición Dinámica de Factores (Stacked Bars):** Gráfico de barras apiladas con menú desplegable (`updatemenus`) para auditar la descomposición aditiva de Cantril Ladder para el Top 15, Bottom 15 y las 10 regiones de la ONU.

---

## 🛠️ 4. Reproducibilidad y Ejecución

Para reproducir todo el flujo analítico desde una terminal:

```bash
# 1. Clonar el repositorio
git clone git@github.com:Juliand10x/Proyecto-2---visualizaci-n.git
cd Proyecto-2---visualizaci-n

# 2. Instalar dependencias necesarias
pip install pandas seaborn plotly openpyxl jinja2 nbconvert

# 3. Ejecutar el Notebook completo y generar el HTML interactivo
jupyter nbconvert --to notebook --execute Equipo_Duarte_Jimenez_Proyecto2_Visualizacion.ipynb

# 4. Compilar el Documento Ejecutivo PDF en LaTeX
pdflatex Equipo_Duarte_Jimenez_Proyecto2_Documento_Ejecutivo.tex
```

---

## 🤖 5. Declaración de Uso de Inteligencia Artificial

Siguiendo las pautas de transparencia de la asignatura, el equipo declara el uso asistencial de **Google Gemini**:
* **Alcance:** Modularización de scripts en Python, calibración de contraste cromático institucional y maquetación tipográfica en LaTeX.
* **Auditoría Humana:** Todos los cálculos, categorizaciones y conclusiones analíticas fueron auditados, validados matemáticamente y redactados bajo criterio exclusivo de los investigadores **Julián Duarte** y **Julián Jiménez**.
