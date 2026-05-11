# Análisis de Variabilidad Hospitalaria — GRD Chile 2023

Segundo avance del proyecto, curso Análisis de Datos e Inferencia Estadística — UDD.

## Integrantes

- Camilo Bufadel — Ingeniería Civil en Informática e Innovación Tecnológica
- Renato Lenis — Ingeniería Civil en Informática e Innovación Tecnológica e Industrial

Docente: Cristian García | Ayudante: Benjamín Bennet

## Pregunta de investigación

¿En qué medida la severidad clínica, el peso GRD, la edad y el sexo del paciente explican
la duración de la hospitalización en hospitales FONASA durante 2023, y persiste variabilidad
entre hospitales al controlar por esos factores?

## Fuente de datos

Datos públicos del Ministerio de Salud (https://datos.gob.cl), separados por pipe |, UTF-8.

- GRD_2023_muestra.csv — 1.039.577 egresos hospitalarios FONASA 2023
- Hospitales.csv — código y nombre de cada hospital
- IR-GRD.csv — grupos diagnósticos GRD
- Severidad.csv — descripción de niveles de severidad

## Estructura

/
├── Codigo/
│   └── GRD_2023_Avance2.ipynb
│   └── Datasets
├── Informe/
│   └── Informe_Avance2_GRD2023.docx
│   └──Informe_Avance2_GRD2023.pdf
├── Presentación/
│   └── Presentacion_GRD2023_Avance2.pptx
├── README.md

## Cómo ejecutar

Python 3.10+. Instalar dependencias:

pip install pandas numpy matplotlib seaborn scipy statsmodels

El dataset debe quedar en datos/datos/GRD_2023_muestra.csv relativo al notebook.
Si está en otra carpeta, cambiar RUTA_GRD en la celda 2:

'RUTA_GRD = r'GRD_2023_muestra.csv''

Ejecutar todas las celdas en orden. Al terminar se generan 9 figuras (fig1 a fig9)
en la misma carpeta del notebook.

## Resultados principales

- ANOVA ESTANCIA ~ SEVERIDAD: F=51.423, p<0,001, η²=12,9%
- Tukey HSD: los 6 pares de severidad son significativos (p<0,001)
- Chi² mortalidad × severidad: χ²=76.265, p<0,001
- Regresión lineal múltiple: R²=24,75%, β_PESO=+4,35 días por unidad de peso GRD
- Variabilidad inter-hospitalaria: rango 2,98–10,05 días entre 68 hospitales (CV=0,229)