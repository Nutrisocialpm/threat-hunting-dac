# UC-WAF-001 - Enumeración de rutas en OCI WAF

## Objetivo

Detectar actividad compatible con reconocimiento activo o enumeración de rutas contra aplicaciones protegidas por OCI WAF.

## Hipótesis

Un actor externo podría intentar descubrir rutas sensibles, paneles administrativos, archivos expuestos, componentes Oracle, endpoints de API o rutas de diagnóstico como fase previa a explotación.

## Fuente de datos

- Plataforma: Microsoft Sentinel
- Tabla: OCI_LogsV2_CL
- Tecnología: OCI WAF
- Lenguaje: KQL

## Criterios de sospecha

- Múltiples rutas únicas desde una misma IP origen.
- Solicitudes a rutas sensibles o de administración.
- Alto volumen de códigos HTTP 400, 401, 403, 404 o 405.
- Tráfico permitido por WAF pero rechazado por backend.
- Actividad contra uno o más hosts en una ventana temporal corta.

## Falsos positivos esperados

- Scanners autorizados.
- Pruebas de pentest.
- Monitoreo sintético.
- Pruebas QA.
- Bots legítimos.
- Validadores externos de disponibilidad.

## Mapeos

### MITRE ATT&CK

- Táctica: Reconnaissance
- Técnica: T1595 - Active Scanning

### OWASP

- Information Gathering.
- Fingerprint Web Application.
- Identify Application Entry Points.
- Security Misconfiguration.

### FIRST CSIRT

- Information Security Event Management.
- Information Security Incident Management.
- Situational Awareness.

## Estado

Hunting validado / Pendiente de aprobación operativa.