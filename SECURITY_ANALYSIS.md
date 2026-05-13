# Análisis de Seguridad: Oaxacoders.org

## Evaluación de Vulnerabilidades

**Fecha:** Mayo 2026
**Versión:** 1.0

---

## Resumen Ejecutivo

Oaxacoders.org es un sitio estático generado con Jekyll que sirve como portal comunitario para programadores en Oaxaca, México. Este documento analiza las vulnerabilidades actuales y las mitigaciones implementadas.

**Nivel de Riesgo:** MEDIO

---

## 1. Arquitectura del Sistema

- **Generador:** Jekyll 4.x
- **CSS Framework:** Tailwind CSS (CDN)
- **Hosting:** GitHub Pages
- **Newsletter:** Buttondown API

---

## 2. Headers de Seguridad Implementados

| Header | Valor | Propósito |
|--------|-------|-----------|
| Strict-Transport-Security | max-age=31536000; includeSubDomains; preload | Fuerza HTTPS |
| X-Content-Type-Options | nosniff | Previene MIME sniffing |
| X-XSS-Protection | 1; mode=block | Protección XSS legacy |
| Referrer-Policy | strict-origin-when-cross-origin | Control de referrer |
| Permissions-Policy | camera=(), microphone=(), geolocation=() | Restricción APIs del navegador |

---

## 3. Validación de Formularios

El formulario de newsletter ahora incluye:
- Validación de patrón regex para formato de email
- Atributo `autocomplete="email"` para mejor UX
- Validación nativa HTML5

---

## 4. Recomendaciones Futuras

1. Implementar CSP cuando los scripts inline sean migrados a archivos externos
2. Añadir SRI (Subresource Integrity) para CDNs
3. Implementar rate limiting en APIs externas
4. Configurar CODEOWNERS para revisión obligatoria

---

## 5. Notas

- Este PR implementa headers de seguridad básicos sin romper funcionalidad existente
- El CSP está pendiente hasta que los scripts inline sean refactorizados