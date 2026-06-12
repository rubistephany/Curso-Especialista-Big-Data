# Curso de Especialista en Big Data 🚀

Este repositorio centraliza todos los proyectos, laboratorios y prácticas desarrolladas a lo largo de la especialización en Big Data e Ingeniería de Datos.

## 📂 Portafolio de Proyectos

* **Proyecto 1: Arquitectura Medallion en Lakehouse**
    * **Descripción:** Implementación de un pipeline de datos completo (Bronze, Silver, Gold) utilizando Docker, Apache Spark, PySpark y Delta Lake. Incluye limpieza de datos y tablas de cuarentena.
    * **Enlace al proyecto:** [lakehouse-docker-retailnova](https://github.com/rubistephany/lakehouse-docker-retailnova)

* **Proyecto 2: Gobernanza de Datos**
    * **Descripción:** Prácticas iniciales sobre control y gobernanza de la información.
    * **Enlace al proyecto:** [practica-data-gov-marquez](https://github.com/rubistephany/practica-data-gov-marquez)
![Uploading image.png…]()

# Cuadro Resumen Integral: VestaMarket S.A. vs. DataStream Corp

| Criterio | VestaMarket S.A. (Streaming 🔀) | DataStream Corp / BigData Lab (Híbrido 🔄) |
| :--- | :--- | :--- |
| **Paradigma Principal** | **Streaming (Tiempo Real):** Flujo continuo de eventos mediante una Arquitectura Orientada a Eventos (EDA). Los datos se procesan de forma inmediata en cuanto nacen. | **Híbrido (Batch + Stream):** Predominio de procesamiento por lotes (*Batch*) con Apache Spark para datos masivos históricos, apoyado en Flink para la ingesta. |
| **Origen del Problema** | Colapso del canal de ventas en el *Black Friday* por peticiones síncronas HTTP/REST y bloqueos en base de datos. Latencias de hasta 4 horas. | Incidente crítico en producción: caída completa de la plataforma Cloud Native por 6 horas debido a configuraciones erróneas en el entorno. |
| **Tecnologías Clave** | Apache Kafka (modo KRaft sin ZooKeeper), scripts en Python (productores y consumidores) y migración a Azure Event Hubs. | Docker, Kubernetes, Apache Spark (Batch), Apache Flink (Stream), Hadoop HDFS y Prometheus. |
| **Enfoque del Rol** | **Data Engineer Puro:** Creación de pipelines, lógica de código, serialización de mensajes JSON y enrutamiento por clave (`id_tienda`). | **DevOps / Big Data Infrastructure:** Reparación de imágenes Docker, manifiestos de Kubernetes, seguridad de usuarios no-root y depuración de la JVM. |
| **Garantía y Fiabilidad** | Lógica en el flujo: configuración de réplicas (`acks=all`), reintentos (`retries=5`) y desactivación del auto-commit para asegurar cada ticket. | Infraestructura en el clúster: configuración de almacenamiento persistente (PVC) en HDFS para que los datos no se borren al reiniciar los pods. |
| **Monitoreo Crítico** | Control del **Consumer Lag** (mide los mensajes acumulados en cola esperando ser procesados por la auditoría de stock). | Control de salud del clúster (estado de los pods, uso de CPU y memoria de Spark/Flink) en tiempo real mediante **Prometheus**. |
| **Similitudes Clave** | Ambos proyectos buscan transformar sistemas antiguos y lentos (*legacy*) que fallaron bajo alta carga. Ambos usan **Docker** localmente para empaquetar y aislar los servicios. Ambos se estructuran mediante archivos **YAML** (docker-compose y manifiestos de Kubernetes) y en ambos se enfatiza la regla de oro de **fijar las versiones estables (LTS)** evitando la etiqueta `latest`. | Ambos proyectos buscan transformar sistemas antiguos y lentos (*legacy*) que fallaron bajo alta carga. Ambos usan **Docker** localmente para empaquetar y aislar los servicios. Ambos se estructuran mediante archivos **YAML** (docker-compose y manifiestos de Kubernetes) y en ambos se enfatiza la regla de oro de **fijar las versiones estables (LTS)** evitando la etiqueta `latest`. |

