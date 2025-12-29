# 🍽️ Sistema de Gestión de Restaurante (Microservicios)

Este proyecto implementa una solución distribuida para la gestión integral de un restaurante utilizando una arquitectura de **Microservicios** con el ecosistema **Spring Cloud**. El sistema permite administrar inventario (ingredientes), menús, reservas y orquestar operaciones complejas entre ellos.

## 📖 Descripción del Proyecto

El sistema está dividido en múltiples servicios independientes que se comunican entre sí para ofrecer las funcionalidades del restaurante. Incluye patrones de arquitectura como **Configuración Centralizada**, **Descubrimiento de Servicios (Eureka)** y **Balanceo de Carga** (ejecutando múltiples instancias de los servicios de negocio).

### 🏗️ Arquitectura del Sistema

El proyecto consta de los siguientes módulos:

* **Infraestructura:**
    * **Config Server** (`config_server`): Servidor centralizado para gestionar las configuraciones de todos los microservicios.
    * **Eureka Server** (`eureka_server`): Servidor de descubrimiento (Service Discovery) donde se registran todos los servicios activos.

* **Microservicios de Negocio:**
    * **mc_ingredientes**: Gestión del stock y proveedores de ingredientes.
    * **mc_menu**: Gestión de platos, menús y su composición.
    * **mc_reservas**: Gestión de mesas y reservas de clientes.
    * **mc_general**: Orquestador que consume los otros servicios para flujos complejos.

---

## 🚀 Tecnologías Utilizadas

* **Lenguaje:** [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html).
* **Gestor de Dependencias:** [Maven](https://maven.apache.org/).
* **Framework Principal:** Spring Boot (v2.7.x / v3.x).
* **Ecosistema Cloud:**
    * Spring Cloud Config.
    * Spring Cloud Netflix Eureka.
    * Spring Cloud OpenFeign (para comunicación entre microservicios).
* **Base de Datos:** HSQLDB (Base de datos en memoria para desarrollo/pruebas).
* **Documentación API:** SpringDoc OpenAPI / Swagger UI.

---

## ⚙️ Instalación y Requisitos

### Prerrequisitos
Asegúrate de tener instalado y configurado en tu entorno:
1.  **Java JDK 17**: Es obligatorio ya que es la versión base definida en los `pom.xml`.
2.  **Apache Maven**: Para la compilación y gestión de dependencias.

### 📥 Pasos de Instalación

1.  **Clonar el repositorio:**
    ```bash
    git clone <URL_DEL_REPOSITORIO>
    cd GestionRestaurante
    ```

2.  **Configurar rutas (Opcional):**
    Si vas a utilizar los scripts automáticos proporcionados, abre los archivos `.bat` y ajusta la variable `BASE_DIR` para que apunte a la carpeta donde clonaste el proyecto en tu máquina.

    ```bat
    set BASE_DIR=C:\Ruta\A\Tu\Proyecto
    ```

---

## ▶️ Ejecución del Proyecto

El proyecto incluye scripts automatizados para facilitar la compilación y el despliegue en local.

### 1. Compilación (Build)
Ejecuta el script de compilación para generar los `.jar` de todos los microservicios:

```bash
script_compilacion_empaquetado.bat
