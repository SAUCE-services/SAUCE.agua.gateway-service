# SAUCE.agua.gateway-service

## Estado del Proyecto

[![Build & Deploy](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/maven.yml/badge.svg)](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/maven.yml)
[![Documentation Status](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/pages.yml/badge.svg)](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/actions/workflows/pages.yml)

## Tecnologías Usadas

![Java](https://img.shields.io/badge/Java-21-blue?logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-brightgreen?logo=spring-boot)
![Maven](https://img.shields.io/badge/Maven-3.x-C71A36?logo=apache-maven)
![Docker](https://img.shields.io/badge/Docker-%231572B6.svg?logo=docker&logoColor=white)

Gateway Service para la arquitectura de microservicios de SAUCE Agua. Este servicio actúa como punto de entrada único para todas las peticiones API, proporcionando enrutamiento dinámico a los diferentes microservicios.

## Enlaces Importantes

- [Documentación del Proyecto](https://sauce-services.github.io/SAUCE.agua.gateway-service)
- [Wiki del Proyecto](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/wiki)
- [Registro de Issues](https://github.com/SAUCE-services/SAUCE.agua.gateway-service/issues)

## Características

- Enrutamiento dinámico basado en Spring Cloud Gateway
- Descubrimiento de servicios con Eureka
- Monitorización mediante Spring Boot Actuator
- Configuración dinámica
- Soporte para balanceo de carga

## Rutas Configuradas

El gateway proporciona acceso a los siguientes servicios:

- `/api/core/**` → Core Service
- `/api/report/**` → Report Service
- `/api/afipws/**` → PyAFIPWS Service

## Requisitos

- Java 21
- Maven 3.x
- Docker (opcional)

## Configuración

### Variables de Entorno

- `APP_PORT`: Puerto del servicio (default: 8080)
- `APP_EUREKA`: Puerto de Eureka (default: 8761)

## Desarrollo

### Construcción

```bash
mvn clean verify install
```

### Ejecución Local

```bash
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
- Estado actual de los Milestones
- Lista de Issues activos y cerrados
- Historial de cambios

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

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0 - ver el archivo [LICENSE](LICENSE) para más detalles.
