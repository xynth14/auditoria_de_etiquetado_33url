# Auditoría de etiquetado · 33 URLs del Portal Claro Perú

Auditoría de todos los elementos interactivos de 33 URLs del Portal Claro Perú (www.claro.com.pe), de la cabecera al footer. Se revisó, en Desktop y en Móvil, si cada elemento dispara el evento de etiquetado GA4 `csa.ga4.event` del contenedor GTM-W8DS3KZ.

## Contenido

| Archivo | Qué muestra |
|---|---|
| `index.html` | Dashboard: indicadores generales, etiquetados vs. sin etiquetar, cobertura por zona de la página (Header, Cuerpo, Footer, Widgets), casos clave sin etiquetar y su impacto, cobertura por URL y metodología y criterios. |
| `detalle.html` | Detalle de las 33 URLs en acordeón: cada elemento con su sección, estado, presencia en Desktop/Móvil, evento que dispara y nota. Incluye buscador, filtros por estado y dispositivo, y la prueba con interacción real de los formularios y del buscador. |
| `comparativa.html` | Header y footer: Portal `/personas/` frente a las variantes `/personas-a/` y `/personas-b/`. Cobertura por zona, prueba de por qué el header de las variantes no etiqueta y qué cambió en su estructura. |
| `causas.html` | Análisis de causas de los elementos sin etiquetar: agrupados por causa y por origen (del sitio, cobertura del etiquetado, condicional), detalle de cada causa con enlaces directos a los componentes, y cambios del sitio detectados en el historial público (Wayback Machine). |

Para verlo, abre `index.html` en el navegador. Desde ahí se navega a las demás páginas por las pestañas superiores.

## Resultados principales

- **11.119 elementos interactivos auditados** (sin contar 36 controles internos de Google Maps y Google Translate).
- **Cobertura total: 84,7 %**: 9.406 elementos etiquetados y 13 parciales (etiquetan solo en un dispositivo).
- **1.700 elementos sin etiquetar (15,3 %).** El 54 % está en el header: menú móvil, buscador y el header completo de `/personas-a/` y `/personas-b/`.
- **Footer prácticamente completo:** 99,7 %.
- **Header de las variantes A/B:** 0 % etiquetado frente a 88,5 % en el Portal. Las variantes usan un header con otra estructura de clases que el etiquetado existente no reconoce.
- **Origen de lo no etiquetado:** 470 elementos (27,6 %) por estructura del sitio o componentes sin etiquetado definido, 1.222 (71,9 %) por cobertura del etiquetado y 8 (0,5 %) condicionales (solo aparecen en ciertos escenarios).
- **Cambios del sitio:** en 12 de las 33 páginas el sitio reemplazó componentes que el etiquetado tenía contemplados; en 5 de ellas quedaron 82 elementos nuevos sin medir.

## Metodología

1. Cada URL se cargó en Chrome en Desktop (1366×900) y en Móvil (390×844), con GTM y los scripts de etiquetado publicados.
2. Se recorrió la página completa para cargar el contenido diferido y se inventariaron todos los elementos interactivos: enlaces, botones, pestañas, flechas y puntos de carruseles, acordeones, campos de formulario, selects, checkboxes y widgets.
3. Se interactuó con cada elemento y se registró lo que llegó al `dataLayer`. Durante la prueba se bloquearon los hits a GA4, Ads y píxeles, para no afectar la analítica de producción.
4. Los formularios de lead («Quiero que me llamen») y el buscador del header se verificaron aparte con interacción real y envío real, usando datos de prueba con el prefijo «Test-».

## Criterios de estado

- **Etiquetado:** el clic dispara al menos un evento GA4 de interacción.
- **Parcial:** el elemento existe en ambos dispositivos pero solo etiqueta en uno.
- **Sin etiquetar:** no dispara ningún evento de interacción. Incluye los enlaces que solo disparan `claro.mkt.derivation.click` (derivación genérica a Tienda, sin sección ni label).
- **No aplica:** controles internos de componentes de terceros (Google Maps, Google Translate). No cuentan en la cobertura.

## URLs auditadas

```
/personas/
/personas-a/
/personas-b/
/personas/movil/postpago/
/personas/movil/postpago/nuevo-postpago/
/personas/movil/prepago/
/personas/movil/prepago/crece-tu-recarga/
/personas/movil/prepago/plan-prepagado/
/personas/movil/prepago/paquetes/
/personas/movil/prepago/bono-inicial/
/personas/beneficios/full-claro/
/personas/beneficios/claro-club/canje-claro-puntos/
/personas/beneficios/claro-club/millas-latam-pass/
/personas/tienda/celulares/
/personas/tienda/nuevos-lanzamientos/iphone-15/
/personas/tienda/nuevos-lanzamientos/iphone-16/
/personas/tienda/nuevos-lanzamientos/iphone-17/
/personas/tienda/nuevos-lanzamientos/galaxy-s23/
/personas/tienda/nuevos-lanzamientos/galaxy-s24/
/personas/tienda/nuevos-lanzamientos/galaxy-s25/
/personas/tienda/nuevos-lanzamientos/galaxy-s26/
/personas/hogar/
/personas/hogar/internet/
/personas/hogar/internet-inalambrico/
/personas/hogar/plan-ideal/
/personas/hogar/tv/canales-digitales/
/personas/olo/internet-portatil/
/portabilidad/
/renovacion/
/consulta-de-numero/
/cobertura/
/hazlorealidad/
/mide-tu-velocidad/
```

Fecha de la auditoría: octubre de 2026.
