# Evaluación de Riesgo Hipotecario con Inteligencia Artificial

Proyecto académico desarrollado para la materia de **Gestión de Proyectos de Inteligencia Artificial**.

El objetivo del proyecto es construir una solución técnica completa, funcional y desplegable para evaluar el riesgo de incumplimiento en una cartera ficticia de clientes hipotecarios. La solución integra generación de datos sintéticos, entrenamiento de un modelo de machine learning, exposición del modelo mediante una API, interfaz frontend, pruebas funcionales, contenedorización con Docker y una propuesta teórica de despliegue en AWS SageMaker AI.

> **Nota importante:** Este proyecto utiliza datos 100% sintéticos y tiene fines exclusivamente académicos. No debe utilizarse para tomar decisiones reales de crédito.

---

## 1. Descripción del problema

En el área de créditos hipotecarios, la evaluación del riesgo de incumplimiento es una actividad crítica para determinar si una solicitud debe ser preaprobada, revisada manualmente o rechazada bajo las condiciones actuales.

Este proyecto simula una solución para estimar la probabilidad de incumplimiento de un cliente hipotecario utilizando variables financieras y de perfil, tales como:

- Edad del solicitante.
- Ingreso mensual.
- Antigüedad laboral.
- Score de buró ficticio.
- Número de atrasos en los últimos 12 meses.
- Monto solicitado del crédito.
- Valor de la vivienda.
- LTV.
- Relación deuda/ingreso.
- Tipo de empleo.
- Canal de originación.
- Zona de residencia o garantía.

La salida del sistema incluye una probabilidad de incumplimiento, un nivel de riesgo, una decisión sugerida y factores explicativos del resultado.

---

## 2. Objetivo del proyecto

Desarrollar una aplicación basada en inteligencia artificial que permita evaluar el riesgo hipotecario de clientes ficticios, integrando un modelo predictivo con una API, una interfaz de usuario, pruebas funcionales y archivos de configuración para despliegue local mediante Docker.

---

## 3. Arquitectura general

La solución está compuesta por los siguientes módulos:

1. **Generación de datos sintéticos**  
   Se crea una cartera ficticia de clientes hipotecarios con variables financieras, demográficas y crediticias.

2. **Entrenamiento del modelo**  
   Se entrena un modelo de clasificación utilizando `scikit-learn`.

3. **Backend/API**  
   Se desarrolla una API con `FastAPI` para exponer el modelo mediante endpoints.

4. **Frontend**  
   Se construye una interfaz sencilla con `Streamlit` para capturar datos del cliente y visualizar el resultado.

5. **Pruebas**  
   Se incluyen pruebas funcionales con `pytest` para validar el comportamiento de la API.

6. **Docker**  
   Se agregan archivos `Dockerfile`, `Dockerfile.frontend` y `docker-compose.yml` para ejecutar la solución en contenedores.

7. **Despliegue teórico en nube**  
   Se documenta cómo podría migrarse la solución a AWS SageMaker AI.

---

## 4. Estructura del proyecto

```text
bbva_mortgage_risk_project/
│
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── model_utils.py
│   ├── risk_rules.py
│   └── schemas.py
│
├── data/
│   └── clientes_hipotecarios.csv
│
├── frontend/
│   └── streamlit_app.py
│
├── models/
│   ├── modelo_riesgo_hipotecario.pkl
│   └── modelo_metadata.json
│
├── tests/
│   └── test_api.py
│
├── train_model.py
├── requirements.txt
├── Dockerfile
├── Dockerfile.frontend
├── docker-compose.yml
├── .gitignore
├── .dockerignore
└── README.md
