# PENDIENTES DE REVISIÓN (CEO) — Réplica estándar Chile v6 → EducaProject Perú

Réplica LOCAL del 2026-07-02. NO desplegado (commit local, sin push). Todo lo listado
aquí quedó SUPUESTO o pendiente de confirmar; el resto se recicló del repo Perú anterior.

## 1. PRECIOS (lo más importante de validar)

### /precios/ (tesis) — MONTOS SUPUESTOS
No existían montos en soles en el repo Perú (la página anterior decía "cotiza por WhatsApp").
Se replicó la matriz de Chile convertida a soles (aprox. CLP→PEN y redondeado). Confirmar TODOS:

| Nivel | Estándar | Preferente | Élite |
|---|---|---|---|
| Instituto | S/ 900 | S/ 1,500 | S/ 2,250 |
| Universidad (Pregrado) | S/ 1,400 | S/ 2,350 | S/ 3,500 |
| Maestría | S/ 2,100 | S/ 3,500 | S/ 5,250 |
| Doctorado | S/ 3,700 | S/ 6,200 | S/ 9,250 |

- Se quitó el nivel "CFT" (no existe en Perú); quedaron 4 pestañas.
- **"Hasta 4 cuotas sin interés" y "20% de descuento al contado"**: son política comercial de
  CHILE replicada tal cual. Confirmar si aplica en Perú (si no, se retira esa sección).
- "+500 tesis entregadas en 2025 · 98% de aprobación": claim heredado de Chile. Confirmar.
- Aviso "Precios referenciales; se confirman con un asesor" agregado (hero + pie).

### /precios-trabajos/ — MONTO SUPUESTO
- "Trabajos cortos desde **S/ 60**" (Chile: $15.000 CLP ≈ S/ 58). Confirmar monto.
- Aviso referencial incluido al pie.

## 2. Números y datos de contacto
- WhatsApp de producción aplicado en TODO el sitio: **+51 922 503 398** (CONFIG y fallbacks HTML).
- **Yape sigue siendo 965 148 374** (reciclado tal cual del pago.html anterior, junto con el
  CCI BCP 00219400170072806990 e IZIPAY/BCP POS). OJO: 965 148 374 era además el número de
  WhatsApp viejo → confirmar que el Yape sigue siendo esa cuenta.
- Redes (recicladas del repo PE): Facebook id=61550076753079, TikTok @educaproject_,
  Instagram @educaproject_peru.

## 3. Testimonios / opiniones (SUPUESTOS)
- Home (trabajos): se adaptaron los 6 testimonios de Chile a nombres/universidades de Perú
  (María Fernández UPN, José Ramírez UPC, Andrea Quispe UCV, Martín Huamán UNI, Lucía Torres
  USMP, Renzo Castillo ULima) y nota "19" (escala 0–20). Son ficticios/adaptados: validar.
- /tesis/: se reutilizaron los testimonios que ya tenía la web PE (mismos textos, unis PE).

## 4. Garantía de notas
- Chile decía "garantizamos notas entre 6,0 y 7,0". Se cambió a **"notas altas (17 a 20)"**
  en FAQ, procedimiento y nosotros. Confirmar la redacción/escala y si se quiere garantizar.

## 5. Referencias
- /referencias/ tiene la MISMA página que Chile (grilla 8 + lightbox + CTA) pero con 8 tarjetas
  promocionales de marca como PLACEHOLDER: NO existen capturas reales de WhatsApp de Perú
  (Chile usa capturas reales en assets/referencias; la carpeta E:\_EVIDENCIAS_WEB\PE está vacía).
  Cuando el CEO entregue capturas reales editadas de Perú, reemplazar assets/referencias/ref-1..8.webp
  (mismo patrón que Chile: 1 tarjeta intro de marca + 7 capturas reales anonimizadas).
  El texto del hero ya quedó idéntico al molde (2026-07-03).

## 6. Blog
- Se migraron los 5 posts de TESIS existentes de Perú a carpetas (/blog/<slug>/) con el diseño
  del molde. El estándar canónico pide posts de TRABAJOS (Power BI, Excel, SQL…) localizados:
  queda pendiente redactarlos para Perú (Chile los tiene como referencia).

## 7. Textos menores
- El molde de Chile trae varias páginas escritas sin tildes (p. ej. el home: "trabajos academicos").
  Se mantuvo idéntico al molde; si se quiere, se corrige ortografía en una pasada aparte
  (aplicaría también a Chile para mantener el estándar).
- FAQ "¿Hacen pruebas o exámenes en línea?" — heredado de Chile; confirmar que aplica en Perú.
- Botón naranja "Cotizar ahora" en /precios/ (acento del molde). Se mantuvo.

## 8. CONTRASTE (pasada visual realizada con capturas de las 14 páginas)
Ajustes aplicados (solo colores, sin tocar reglas estructurales, salvo 2 reglas nuevas de color
y un `white-space:nowrap` para el número del nav):
- Sección "Opiniones" (home y tesis): fondo foto-oscuro del molde dejaba el título/subtítulo
  invisibles → título blanco + subtítulo rgba(255,255,255,.85) + subrayado blanco (regla nueva).
- Bandas "urgente" y "final CTA": gradiente amarillo→ahora azul (#1A3A6B→#4D7EDD) con textos
  blancos; botón primario blanco con texto azul; botón fantasma transparente con borde/texto blanco.
- Botones primarios/nav/step/tags/mockup/to-top: texto charcoal (#2D2D2D pensado para amarillo)
  → blanco sobre el azul de marca.
- Fondos cálidos (#FFFBF0/#FFF8E1/#FFF7E0) → equivalentes azul pálido (#F5F8FE/#EDF3FD/#EFF4FD).
- Paleta: --brand #3C5EB3, --brand2 #4D7EDD, --brand-ink #1F3A78, --brand3 #E7EDFB,
  --gold(alias) #3C5EB3, --gold-d #2D4A94. Tintes rgba(247,201,72)→rgba(60,94,179).
- Número de WhatsApp del nav se partía en 4 líneas en páginas con menú largo → nowrap.
- Bug del molde arrastrado: imágenes con src relativo "Imagenes/…" rotas en /blog/ y /tesis/
  → se pasaron a "/Imagenes/…" (Chile tiene el mismo bug; conviene replicarlo allá).

## 9. Técnico
- Stubs de redirección creados para TODOS los .html viejos (compatibilidad con links del bot):
  procedimiento.html → /procedimiento/, blog-*.html → /blog/<slug>/, etc. (14 stubs, meta refresh
  + canonical a educaproject.ags-ed.com + location.replace).
- Sin /cotizador/ (el CTA "solo una parte de tu tesis" ahora abre WhatsApp).
- app.js incluye la red de seguridad de reveal (setTimeout 1.5s) tomada del molde parcheado.
- Los archivos v2 anteriores quedan en el historial de git (se sobreescribieron con stubs).
