# Changelog

Todos los cambios notables en este proyecto serán documentados en este archivo.

## [Unreleased]

## [0.0.2] - 2025-12-31

### Changed
- Upgrade JDK from 24 to 25
- Upgrade Spring Boot from 3.5.3 to 3.5.8
- Update Maven Docker image to use JDK 25 (maven:3-eclipse-temurin-25-alpine)
- Update Java runtime Docker image to JRE 25 (eclipse-temurin:25-jre-alpine)
- Minor formatting cleanup in bootstrap.yml

### Added
- Architecture diagrams in Mermaid format
- Service discovery flow documentation

## [0.0.1] - 2025-01-26

### Added
- Implementación de generación automática de Wiki
- Mejoras en el workflow de GitHub Pages
- Integración de permisos mejorados para la documentación

### Changed
- Actualización de Spring Boot de 3.4.1 a 3.4.2

## [0.0.0] - 2024-07-18

### Added
- Configuración inicial del proyecto
- Implementación del servicio Gateway nativo
- Configuración de CI/CD con GitHub Actions
- Primera versión del servicio con:
  - Enrutamiento dinámico
  - Integración con Eureka
  - Configuración de Actuator
  - Soporte para Docker 