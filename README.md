# 🚗 API REST - Sucursal Vehículos (Flujo CI/CD)

Este repositorio contiene el código fuente de la aplicación Spring Boot "Sucursal Vehículos", junto con la automatización de su despliegue continuo (CI/CD) utilizando Jenkins y Docker en infraestructura AWS.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Java 17 (OpenJDK)
* **Framework:** Spring Boot
* **Gestor de Dependencias:** Maven (M3)
* **Orquestación y Contenedores:** Docker
* **Servidor Web:** Apache Tomcat (v10.1.23)
* **CI/CD:** Jenkins
* **Infraestructura:** AWS EC2 (Ubuntu 24.04)

## ⚙️ Arquitectura del Pipeline (Jenkinsfile)
El flujo automatizado consta de las siguientes etapas:
1. **Git Clone:** Obtención automática del código fuente mediante Webhook.
2. **Build Application:** Compilación y empaquetado del proyecto a formato `.war` utilizando Maven (`mvn clean package`).
3. **Creación Imagen Docker:** Construcción de la imagen basada en Tomcat copiando el artefacto compilado.
4. **Despliegue Contenedor Tomcat:** Despliegue de la aplicación mapeando el puerto `9090` del host al `8080` del contenedor.

## 🚀 Despliegue y Pruebas
La aplicación se encuentra desplegada en un contenedor Docker y expone sus servicios a través del puerto `9090`.

* **Acceso a Swagger UI:** `http://<IP_EC2>:9090/vehiculosBuild/swagger-ui.html`
* **Pruebas de Integración:** Utilizar Postman para realizar peticiones HTTP (GET, POST, PUT, DELETE) hacia los endpoints definidos en el controlador REST.
