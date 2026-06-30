# Lógica del caso de uso

## Descripción

El caso analiza eventos de OCI WAF en Microsoft Sentinel para identificar actividad compatible con enumeración de rutas o reconocimiento web.

La lógica se basa en agrupar solicitudes por IP origen, host destino y ventana temporal. Se consideran candidatas aquellas IPs que generan múltiples rutas únicas o rutas clasificadas como sospechosas.

## Condiciones principales

- `WAFAction == allow`
- `StatusCode` en 400, 401, 403, 404 o 405
- IP origen pública
- Host válido
- Path informado
- Respuesta no generada directamente por WAF, cuando el campo `ResponseProvider` lo permita validar

## Umbrales iniciales

| Parámetro | Valor |
|---|---:|
| Lookback | 1 hora |
| Ventana | 15 minutos |
| Endpoints únicos mínimos | 3 |
| Rutas sospechosas únicas mínimas | 2 |

## Interpretación

El caso no confirma explotación. Genera un candidato de hallazgo o alerta que debe validarse con contexto del cliente.