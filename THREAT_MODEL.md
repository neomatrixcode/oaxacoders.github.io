# Modelo de Amenazas: Oaxacoders.org

## Análisis de Amenazas y Mitigaciones

**Fecha:** Mayo 2026
**Versión:** 1.0

---

## 1. Actores de Amenaza

| Actor | Capacidad | Motivación |
|-------|-----------|------------|
| Script Kiddies | Baja | Diversión |
| Cyber Criminales | Media | Financiero |
| Estado-Nación APT | Muy Alta | Espionaje |

---

## 2. Análisis STRIDE

### Security Headers implementados mitigan:

| Categoría | Amenaza | Mitigación |
|-----------|---------|-----------|
| Information Disclosure | Fingerprinting via headers | Headers de seguridad estandarizados |
| XSS | reflected XSS | X-XSS-Protection enabled |
| MitM | Interceptación tráfico | HSTS forzado |

---

## 3. Controles de Seguridad Activos

- **HTTPS:** Forzado via HSTS preload
- **X-Frame-Options:** Legacy (no moderno)
- **Content-Type Sniffing:** Bloqueado via X-Content-Type-Options
- **Referrer Policy:** strict-origin-when-cross-origin

---

## 4. Amenazas Pendientes

| Amenaza | Riesgo | Acción Recomendada |
|---------|--------|-------------------|
| CSP no implementado | Alto | Migrar scripts a archivos externos |
| SRI no implementado | Medio | Añadir integrity hashes a CDNs |
| Scripts inline | Medio | Refactorizar menu.js |

---

## 5. Plan de Respuesta a Incidentes

| Nivel | Tiempo de Respuesta | Ejemplo |
|-------|-------------------|---------|
| P1 Crítico | < 1 hora | Backdoor activo |
| P2 Alto | < 4 horas | Secrets expuestos |
| P3 Medio | < 24 horas | DDoS, phishing attempts |

---

*Documento para uso interno del equipo Oaxacoders*