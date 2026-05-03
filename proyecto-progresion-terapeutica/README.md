# Modelización de la progresión terapéutica en pacientes con patologías crónicas

Proyecto de análisis y modelización orientado a reconstruir la evolución terapéutica de pacientes con síndrome metabólico a partir de datos de dispensación farmacéutica, con el objetivo de identificar patrones de progresión y predecir la intensificación del tratamiento.

---

## Presentación del proyecto
[Ver presentación (resumen ejecutivo)](presentacion.pdf)

## Informe completo
 [Ver informe detallado](informe.pdf)

## Notebook
[Ver análisis completo (HTML)](analisis.html)

---

## Contexto

El síndrome metabólico representa un conjunto de patologías (hipertensión, dislipemia y diabetes) cuya coexistencia incrementa significativamente el riesgo cardiovascular.

En la práctica clínica, la progresión de estas patologías se traduce en una **intensificación progresiva del tratamiento farmacológico**, reflejando un aumento del riesgo del paciente. Sin embargo, anticipar qué pacientes requerirán esa intensificación sigue siendo un reto, especialmente en entornos con información clínica limitada. :contentReference[oaicite:0]{index=0}

---

## Objetivo

- Analizar la evolución terapéutica de pacientes crónicos  
- Identificar patrones de progresión clínica a partir del tratamiento  
- Desarrollar un modelo capaz de estimar la **probabilidad de intensificación terapéutica**  
- Explorar su aplicación como herramienta de **estratificación de riesgo en entornos reales (farmacia / atención primaria)**  

---

##  Datos

- Fuente: datos de dispensación farmacéutica (práctica real)  
- Variables construidas a partir del consumo de medicamentos como proxy clínico  
- Principales grupos terapéuticos:
  - Hipertensión: enalapril, enalapril/HCTZ, amlodipino  
  - Colesterol: simvastatina  
  - Diabetes: metformina :contentReference[oaicite:1]{index=1}  

Enfoque clave:  
No se dispone de datos clínicos directos → el estado del paciente se **infiere a partir del tratamiento**, lo que convierte el problema en un caso realista de datos imperfectos.

---

## Análisis

### 1. Reconstrucción longitudinal del paciente
- Seguimiento temporal del tratamiento por paciente  
- Identificación de:
  - cambios de dosis  
  - incorporación de nuevos fármacos  
  - escalados terapéuticos  

👉 Permite reconstruir la evolución clínica a partir de datos administrativos :contentReference[oaicite:2]{index=2}  

---

### 2. Definición de progresión terapéutica
- Progresión = aumento de complejidad del tratamiento  
- Segmentación de pacientes:
  - progresión (intensificación)  
  - estabilidad / reducción  

---

### 3. Análisis de patrones

- La mayoría de pacientes comienza con una única patología  
- La progresión ocurre de forma **gradual y acumulativa**  
- La intensificación se concentra en pacientes con **mayor carga metabólica** :contentReference[oaicite:3]{index=3}  

Insight clave: el riesgo no depende de una variable aislada, sino de la **complejidad global del paciente**

---

### 4. Modelización

- Modelo predictivo para estimar probabilidad de intensificación  
- Estratificación de riesgo:
  - Bajo (<0.5)  
  - Moderado (0.5–0.8)  
  - Alto (>0.8) :contentReference[oaicite:4]{index=4}  

 Enfoque:
- Modelo interpretable  
- Orientado a priorización, no a diagnóstico  

---

## Insights clave

- La **acumulación de patologías** es el principal driver de intensificación  
- El modelo identifica mejor:
  - pacientes en fases avanzadas  
  - perfiles de alto riesgo  

- Menor capacidad en:
  - fases iniciales  
  - progresión temprana  

- Existen pacientes de alto riesgo que aún no han intensificado tratamiento →  
  👉 potencial uso predictivo real (no solo retrospectivo) :contentReference[oaicite:5]{index=5}  

---

## Limitaciones

Este proyecto está diseñado para mostrar no solo lo que el modelo hace, sino **dónde falla y por qué**:

- Uso de proxies clínicos (medicación ≠ estado clínico real) :contentReference[oaicite:6]{index=6}  
- Censura temporal (datos limitados a 2025)  
- Ruido estructural (compras agregadas por paciente)  
- Falta de variables clínicas:
  - analíticas  
  - adherencia  
  - diagnóstico real  

- Datos de una única farmacia → **limitación de generalización** :contentReference[oaicite:7]{index=7}  

---

## Aplicación práctica

- Identificación proactiva de pacientes de alto riesgo  
- Seguimiento farmacoterapéutico personalizado  
- Potencial integración en:
  - farmacia comunitaria
  - negocios de salud
  - programas de prevención  

Enfoque: **herramienta de apoyo a la decisión, no sustituto clínico**

---

## Valor del proyecto

Este trabajo demuestra que:

- Es posible transformar datos de dispensación en información clínica útil  
- Se pueden construir modelos de riesgo en entornos con datos incompletos  
- La ciencia de datos aplicada a salud real requiere:
  - interpretación  
  - contexto clínico  
  - análisis crítico de limitaciones  

---
