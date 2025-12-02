# OR-Master: Transformación Digital del Quirófano

![Status](https://img.shields.io/badge/Status-Completed-success)
![Area](https://img.shields.io/badge/Area-Health_Operations-blue)
![Tech](https://img.shields.io/badge/AI-Random_Forest-orange)

> **Caso de Estudio:** Optimización de Agendas Quirúrgicas mediante Gemelos Digitales  
> **Fecha:** Diciembre 2025  
> **Autor:** Dr. Wilmar Flores  

---

## 1. Resumen Ejecutivo

Los quirófanos representan el centro de costos y de ingresos más crítico de un hospital. La variabilidad no planificada en la duración de las cirugías genera pérdidas estimadas en **$1,200 USD por hora** debido a tiempos muertos y horas extra.

Este proyecto, **OR-Master**, implementó un "Gemelo Digital" para auditar la eficiencia actual y proponer un modelo de Inteligencia Artificial que optimiza la agenda quirúrgica.

### Resultado Clave
Se identificó un potencial de ahorro de **$19.8 Millones USD anuales** al reducir la incertidumbre de la agenda en un **45%**.

---

## 2. Diagnóstico: ¿Por qué fallamos hoy?

El análisis de **5,000 procedimientos simulados** reveló dos patrones de comportamiento humano que destruyen valor operativo:

### A. El "Efecto Escalón" (Block Scheduling)
Los cirujanos tienden a redondear la duración estimada a bloques de 30 o 60 minutos.
* **Consecuencia:** Se desperdician sistemáticamente entre **15 y 20 minutos por cirugía**, que sumados al año equivalen a cientos de horas de quirófano vacío.

### B. Ceguera ante la Complejidad
La programación manual ignora factores no lineales.
* **Ejemplo:** Un paciente con **IMC > 35** no tarda "un poco más", tarda *exponencialmente* más en cirugías abdominales. El humano no ajusta este riesgo; la IA sí.

---

## 3. La Solución Tecnológica

Se desarrolló un modelo predictivo (**Random Forest Regressor**) entrenado con variables clínicas específicas:

* **Factores del Paciente:** Edad, IMC, Score ASA (Riesgo Anestésico).
* **Factores Operativos:** Curva de aprendizaje del cirujano (Residente vs Senior), Turno (Fatiga nocturna).

### Validación Cruzada
El modelo no solo predice un número, sino que cuantifica el riesgo mejor que la estimación humana:

| Modelo | R² (Coeficiente de Determinación) | Interpretación |
| :--- | :---: | :--- |
| **Estimación Humana** | `0.66` | Alta variabilidad e incertidumbre. |
| **Modelo IA (OR-Master)** | `0.89` | Alta precisión y consistencia. |

---

## 4. Impacto Financiero y Operativo

La implementación de este algoritmo permitiría pasar de una gestión reactiva a una proactiva.

| KPI | Situación Actual | Con Modelo OR-Master | Mejora |
| :--- | :---: | :---: | :--- |
| **Error Promedio (MAE)** | 38 minutos | **21 minutos** | 45% más preciso |
| **Casos Críticos** (>30min desvío) | 43.7% | **23.6%** | Mitad de interrupciones |
| **Costo de Ineficiencia** | Alto (Horas Extra) | Optimizado | $19M USD / año** |

---

## 5. Conclusión

La Inteligencia Artificial no reemplaza el juicio clínico del cirujano dentro del quirófano, pero es una herramienta indispensable para gestionarlo desde fuera.

**OR-Master** demuestra que capturar datos clínicos granulares (como el IMC o ASA) tiene un retorno de inversión directo y masivo en la operación hospitalaria.

---
*© 2025 Dr. Wilmar Flores - Health Data Science Portfolio*
---

## Guía Técnica: Instalación y Uso

Si eres un desarrollador o data scientist y quieres reproducir la simulación:

### 1. Prerrequisitos
Asegúrate de tener Python 3.8+ instalado.

### 2. Instalación
```bash
git clone [https://github.com/willflo11/or-master-surgical-optimization.git](https://github.com/willflo11/or-master-surgical-optimization.git)
cd or-master-surgical-optimization
pip install -r Requirements.txt
python optimizacion_quirófanos.py

