# Threat Hunting Detection-as-Code

Repositorio para la gestión versionada de casos de uso de Threat Hunting, consultas SIEM, reglas Sigma, documentación técnica y evidencias sanitizadas.

## Objetivo

Estandarizar la creación, mantenimiento, revisión y reutilización de casos de uso de Threat Hunting mediante un enfoque Detection-as-Code / Hunting-as-Code.

## Estructura

- `core/`: casos de uso, lógica base, mapeos MITRE, OWASP y FIRST.
- `adapters/`: implementaciones técnicas por plataforma SIEM.
- `clients/`: ajustes específicos por cliente.
- `governance/`: reglas de control de cambios, aprobación y revisión.
- `templates/`: plantillas reutilizables.
- `tests/`: validaciones y resultados sanitizados.
- `docs/`: metodología y arquitectura.
- `reports/`: reportes internos o para cliente.

## Principios

1. Todo caso de uso debe tener ID único.
2. Toda query debe estar versionada.
3. Todo cambio debe registrarse en Git.
4. No se deben subir datos sensibles.
5. MITRE ATT&CK es el marco principal de clasificación.
6. OWASP se usa para casos web, API o WAF.
7. FIRST se usa como referencia operativa CSIRT/SOC.
8. Sigma se usa como formato portable cuando aplique.
9. Las queries nativas se mantienen por plataforma.
