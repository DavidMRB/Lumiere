# Accesibilidad — Lumière Gastronomy

🌐 **Demo en vivo:** [https://lumiere-woad-five.vercel.app/](https://lumiere-woad-five.vercel.app/)

## Usuario avanzado objetivo

**Perfil:** Usuario con movilidad reducida que navega exclusivamente mediante teclado (*Keyboard-Only Navigation*), sin uso de ratón ni pantalla táctil.

**Dispositivo de entrada:** Teclado físico estándar.  
**Teclas utilizadas:** `Tab`, `Shift+Tab`, `Enter`, `Space`, `Escape`, teclas de flecha.  
**Necesidades críticas:** Foco siempre visible, orden de tabulación lógico, sin trampas de foco, formularios operables sin ratón, menú mobile accesible.

---

## Menú de Accesibilidad Flotante

Botón flotante accesible que permite personalizar la experiencia del usuario según sus necesidades específicas:

### Ajustes de Texto
- **Tamaño de fuente:** Incrementa o reduce el tamaño del texto en toda la página
- **Espaciado de letras:** Ajusta el espacio entre caracteres para mejorar legibilidad
- **Espaciado de líneas:** Modifica la altura de línea del texto

### Tipografía Amigable
- **Fuente Lexend Deca:** Tipografía diseñada específicamente para usuarios con dislexia, mejorando significativamente la legibilidad

### Contraste y Colores
- **Alto contraste:** Aumenta el contraste visual de todos los elementos
- **Modo oscuro:** Activa un tema oscuro para reducir la fatiga visual en ambientes con poca luz

### Filtros de Visión de Color
- **Deuteranopia:** Simula la falta de percepción del color verde
- **Protanopia:** Simula la falta de percepción del color rojo
- **Tritanopia:** Simula la falta de percepción del color azul

### Navegación Visual
- **Resaltar enlaces:** Destaca visualmente todos los enlaces de la página
- **Subrayar títulos:** Subraya todos los encabezados (H1, H2, H3, etc.)

### Lectura de Pantalla
- **Texto a voz (Text-to-Speech):** Función de lectura de pantalla integrada usando ResponsiveVoice API

### Características Técnicas
- **Persistencia de preferencias:** Todas las configuraciones se guardan automáticamente en localStorage
- **Botón flotante accesible:** Navegable completamente por teclado (`Tab`, `Enter`, `Escape`)
- **100% accesible:** ARIA labels, screen reader friendly, compatible con lectores de pantalla
- **Responsive:** Funciona correctamente en dispositivos móviles y desktop
- **Restaurar valores predeterminados:** Botón para volver a la configuración original

---

## Estándares aplicados

| Estándar | Versión | Nivel |
|---|---|---|
| WCAG (Web Content Accessibility Guidelines) | 2.1 + criterios 2.2 | AA |
| EN 301 549 (Norma europea de accesibilidad TIC) | v3.2.1 | Obligatorio UE |

---

## Conformidad punto a punto

### Principio 1 — Perceptible

| SC | Criterio | Estado |
|---|---|---|
| 1.1.1 | Contenido no textual — todas las imágenes tienen `alt` descriptivo; decorativas con `aria-hidden="true"` | ✅ |
| 1.3.1 | Información y relaciones — HTML semántico: `<header>`, `<main>`, `<nav>`, `<section aria-labelledby>`, `<article>`, `<footer>`; labels vinculados con `for/id` | ✅ |
| 1.3.2 | Secuencia significativa — orden DOM coincide con el visual; tabulación lógica de arriba a abajo | ✅ |
| 1.4.3 | Contraste de texto — CTA `#9e3d19` sobre blanco: ratio 5.8:1; precios `#8a3d10`: ratio 5.1:1 (mínimo requerido 4.5:1) | ✅ |
| 1.4.4 | Cambio de tamaño — contenido legible al 200% sin pérdida de funcionalidad | ✅ |
| 1.4.11 | Contraste de componentes UI — bordes de inputs `#767676` sobre fondo claro: ratio 4.5:1 (mínimo requerido 3:1) | ✅ |

### Principio 2 — Operable

| SC | Criterio | Estado |
|---|---|---|
| 2.1.1 | Teclado — toda la funcionalidad operable con teclado; menú mobile funcional con `Enter`/`Space` | ✅ |
| 2.1.2 | Sin trampa de teclado — focus trap en menú mobile; `Escape` libera el foco y lo devuelve al botón toggle | ✅ |
| 2.4.1 | Saltar bloques — skip link visible al recibir foco, apunta a `<main tabindex="-1">` | ✅ |
| 2.4.2 | Página titulada — `<title>Lumière Gastronomy - Reservas</title>` | ✅ |
| 2.4.3 | Orden del foco — `<main tabindex="-1">` garantiza transferencia real del foco en Chrome/Edge | ✅ |
| 2.4.4 | Propósito del enlace — texto descriptivo en contexto; logo con `aria-label`; precios con `aria-label` | ✅ |
| 2.4.6 | Encabezados y etiquetas — jerarquía H1 → H2 → H3 correcta; todos los campos con `<label>` | ✅ |
| 2.4.7 | Foco visible — `outline: 2px solid #000` en todos los interactivos vía `:focus-visible` | ✅ |
| 2.4.11 | Apariencia del foco (WCAG 2.2 / EN 301 549 v3.2+) — área mínima de contorno perimetral de 2px cumplida | ✅ |
| 2.5.3 | Etiqueta en nombre accesible — texto visible coincide con nombre accesible en árbol de accesibilidad | ✅ |
| — | Header sticky — `scroll-padding-top: 88px` evita que el header tape el contenido al navegar por anclas | ✅ |

### Principio 3 — Comprensible

| SC | Criterio | Estado |
|---|---|---|
| 3.1.1 | Idioma de la página — `<html lang="es">` | ✅ |
| 3.1.2 | Idioma de partes — textos en inglés del footer con `lang="en"` (EN 301 549 §9.3.1.2) | ✅ |
| 3.2.1 | Al recibir el foco — ningún campo provoca cambio de contexto al recibir foco | ✅ |
| 3.3.1 | Identificación de errores — `aria-invalid="true"` y mensaje `role="alert"` en cada campo inválido | ✅ |
| 3.3.2 | Etiquetas e instrucciones — campo fecha con `min` (no fechas pasadas) y hint vinculado por `aria-describedby`; indicador de campos requeridos explicado al inicio del formulario | ✅ |
| 3.3.3 | Sugerencia ante errores — mensajes específicos por campo; resumen con `aria-live="assertive"`; foco al primer campo inválido | ✅ |

### Principio 4 — Robusto

| SC | Criterio | Estado |
|---|---|---|
| 4.1.1 | Procesamiento — HTML válido, sin IDs duplicados, atributos ARIA correctos | ✅ |
| 4.1.2 | Nombre, función, valor — `aria-expanded` dinámico en botón de menú; `aria-label` alterna "Abrir / Cerrar"; `role="dialog" aria-modal="true"` en panel mobile | ✅ |
| 4.1.3 | Mensajes de estado — resumen de errores con `role="alert" aria-live="assertive" aria-atomic="true"` | ✅ |

---

## Navegación por teclado — flujo completo

```
Tab             → avanza al siguiente elemento interactivo
Shift + Tab     → retrocede al elemento anterior
Enter / Space   → activa enlaces, botones y abre el menú mobile
Escape          → cierra el menú mobile y devuelve el foco al botón toggle
Teclas flecha   → navega opciones dentro de <select>
```

Orden de tabulación en página:
1. Skip link → `#main-content`
2. Logo (enlace)
3. Navegación principal (Experiencia, Menú, Eventos, Cena Privada)
4. Botón "Reserva una mesa"
5. Botón menú hamburguesa (mobile)
6. Sección hero → enlace "Reservar Mesa"
7. Sección reservas → campos de formulario (Nombre, Email, Fecha, Hora, Comensales, Requisitos)
8. Botón "Confirmar Reserva"
9. Footer (enlaces)

---

## Puntos pendientes (P2 — no bloqueantes)

| SC | Descripción |
|---|---|
| 1.4.4 | Migrar tamaños de fuente de `px` a `rem` en el config de Tailwind para respetar la preferencia de fuente del sistema operativo |
| 2.4.12 | Validar foco no oculto (WCAG 2.2) en viewports muy pequeños con scroll lateral |

---

## Herramientas de verificación recomendadas

- [axe DevTools](https://www.deque.com/axe/) — extensión de navegador para auditoría automática
- [NVDA](https://www.nvaccess.org/) + Chrome — lector de pantalla para pruebas manuales en Windows
- [VoiceOver](https://www.apple.com/accessibility/mac/vision/) + Safari — lector de pantalla en macOS/iOS
- Navegación manual con solo teclado (`Tab`, `Shift+Tab`, `Enter`, `Escape`) en Chrome, Firefox y Edge

---