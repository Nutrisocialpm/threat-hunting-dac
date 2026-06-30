# Falsos positivos conocidos

## Posibles fuentes legítimas

- Scanners autorizados.
- Pruebas de pentest.
- Monitoreo sintético.
- Pruebas QA.
- Bots legítimos.
- Validadores de disponibilidad.
- Integraciones externas.

## Validaciones recomendadas

- Verificar si la IP origen pertenece a una lista autorizada.
- Confirmar si hubo actividad planificada.
- Revisar User-Agent.
- Validar si el host es productivo, QA o laboratorio.
- Confirmar si existió respuesta HTTP 200 posterior sobre rutas sensibles.

## Exclusiones sugeridas

- IPs de scanners autorizados.
- IPs de monitoreo.
- Rangos internos aprobados.
- User-Agents de herramientas permitidas.