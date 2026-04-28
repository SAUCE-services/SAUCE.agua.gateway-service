# SAUCE.agua.gateway-service

## Estado del Proyecto

[![Build & Deploy](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/maven.yml/badge.svg)](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/maven.yml)
[![Documentation Status](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/pages.yml/badge.svg)](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/pages.yml)

## Tecnologías Usadas

![Java](https://img.shields.io/badge/Java-25-blue?logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.0.6-brightgreen?logo=spring-boot)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-2025.1.0-brightgreen?logo=spring)
![Maven](https://img.shields.io/badge/Maven-3.x-C71A36?logo=apache-maven)
![Docker](https://img.shields.io/badge/Docker-%231572B6.svg?logo=docker&logoColor=white)
![Consul](https://img.shields.io/badge/Consul-%23F04C53.svg?logo=consul&logoColor=white)

Gateway Service para la arquitectura de microservicios de SAUCE Agua. Este servicio actúa como punto de entrada único para todas las peticiones API, proporcionando enrutamiento dinámico a los diferentes microservicios con integración de Consul para descubrimiento de servicios.

## Enlaces Importantes

- [Documentación del Proyecto](https://sauce-services.github.io/SAUCE.agua.gateway-service)
- [Wiki del Proyecto](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/wiki)
- [Registro de Issues](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/issues)

## Características

- Enrutamiento dinámico basado en Spring Cloud Gateway
- Descubrimiento de servicios con **Consul**
- Monitorización mediante Spring Boot Actuator
- Configuración dinámica con Consul KV
- Soporte para balanceo de carga
- Integración nativa con Docker

## Rutas Configuradas

El gateway proporciona acceso a los siguientes servicios:

- `/api/core/**` → Core Service
- `/api/report/**` → Report Service
- `/api/afipws/**` → PyAFIPWS Service

## Requisitos

- Java 25
- Maven 3.x
- Consul (para descubrimiento de servicios)
- Docker (opcional)

## Configuración

### Variables de Entorno

- `APP_PORT`: Puerto del servicio (default: 8080)
- `APP_CONSUL_HOST`: Host de Consul (default: consul-service)
- `APP_CONSUL_PORT`: Puerto de Consul (default: 8500)

### Consul Configuration

El servicio se registra automáticamente en Consul y utiliza su catálogo de servicios para el descubrimiento dinámico.

## Desarrollo

### Construcción

```bash
mvn clean verify install
```

### Ejecución Local

```bash
# Asegúrate de tener Consul ejecutándose en localhost:8500
mvn spring-boot:run
```

### Docker

Build de la imagen:
```bash
docker build -t sauce.agua.gateway-service .
```

Ejecución con Docker:
```bash
docker run -p 8080:8080 sauce.agua.gateway-service
```

## Documentación

La documentación detallada del proyecto se genera automáticamente y está disponible en GitHub Pages. Incluye:
- Diagramas de arquitectura en formato Mermaid
- Estado actual de los Milestones
- Lista de Issues activos y cerrados
- Historial de cambios

## Arquitectura

![Request Flow](docs/diagrams/request_flow.mmd)

![Gateway Status](docs/diagrams/gateway_status.mmd)

## Monitorización

El servicio expone endpoints de Actuator para monitorización:

- `/actuator/health` - Estado del servicio
- `/actuator/info` - Información del servicio
- `/actuator/metrics` - Métricas del servicio

## CI/CD

El proyecto utiliza GitHub Actions para:
- Construcción y pruebas automáticas
- Generación y despliegue de documentación
- Construcción y publicación de imágenes Docker
- Análisis de código con SonarCloud

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0 - ver el archivo [LICENSE](LICENSE) para más detalles.
