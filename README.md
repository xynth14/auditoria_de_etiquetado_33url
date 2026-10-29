# Auditoría de etiquetado · 33 URLs del Portal Claro Perú

Auditoría de todos los elementos interactivos de 33 URLs del Portal Claro Perú (www.claro.com.pe), de la cabecera al footer. Se revisó, en Desktop y en Móvil, si cada elemento dispara el evento de etiquetado GA4 `csa.ga4.event` del contenedor GTM-W8DS3KZ.

## Contenido

| Archivo | Qué muestra |
|---|---|
| `index.html` | Dashboard: indicadores generales, etiquetados vs. sin etiquetar, cobertura por zona de la página (Header, Cuerpo, Footer, Widgets), cobertura por URL y metodología y criterios. |
| `detalle.html` | Detalle de las 33 URLs en acordeón: cada elemento con su sección, estado, presencia en Desktop/Móvil, evento que dispara y nota. Incluye buscador y filtros por estado y dispositivo. |

Para verlo, abre `index.html` en el navegador. Desde ahí se navega al detalle.

## Resultados principales

- **11.119 elementos interactivos auditados** (sin contar 36 controles internos de Google Maps y Google Translate).
- **Cobertura total: 84,7 %**: 9.406 elementos etiquetados y 13 parciales (etiquetan solo en un dispositivo).
- **1.700 elementos sin etiquetar (15,3 %).** El 54 % está en el header: menú móvil, buscador y el header completo de `/personas-a/` y `/personas-b/`.
- **Footer prácticamente completo:** 99,7 %.

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
