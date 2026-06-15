# ⚡ GUÍA RÁPIDA - CREAR TUS DIAGRAMAS AHORA

## 🚀 START AQUÍ (5 MINUTOS)

### Elige tu herramienta:

```
┌─────────────────────────────────────────────┐
│ DRAW.IO (Más fácil - RECOMENDADO)           │
│ ✓ Sin instalación                           │
│ ✓ Gratis                                    │
│ ✓ Interfaz sencilla                         │
│ → https://app.diagrams.net/                 │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ VISIO (Más profesional)                     │
│ ✓ Tiene tu institución?                     │
│ ✓ Muy completo                              │
│ ✓ Formato .vsdx estándar                    │
│ → Descarga/Suscripción                      │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ LUCIDCHART (Mejor para equipo)              │
│ ✓ Colaboración en tiempo real               │
│ ✓ Free trial 14 días                        │
│ ✓ Mejor UX                                  │
│ → https://www.lucidchart.com/               │
└─────────────────────────────────────────────┘
```

---

## 📋 LOS 4 DIAGRAMAS A CREAR

### 1️⃣ DIAGRAMA DE ARQUITECTURA
**Tiempo: 15 minutos**

```
┌────────────────────────────────┐
│    Navegador (Usuario)         │
└────────────┬───────────────────┘
             │ HTTP/HTTPS
             ▼
┌────────────────────────────────┐
│    Azure App Service           │
└────────────┬───────────────────┘
             │
      ┌──────┼──────┐
      ▼      ▼      ▼
   HTML    CSS    JavaScript
      │      │      │
      └──────┼──────┘
             ▼
       ┌─────────────────┐
       │ Secciones Web:  │
       │ • Hero          │
       │ • Servicios     │
       │ • Nosotros      │
       │ • Contacto      │
       └─────────────────┘
```

**Qué incluir:**
- 8 cajas (Usuario, App Service, HTML, CSS, JS, Assets, Secciones, Subsecciones)
- Líneas conectando
- 6 colores diferentes

---

### 2️⃣ DIAGRAMA DE INFRAESTRUCTURA AZURE
**Tiempo: 20 minutos**

```
        ┌─────────────────────────────────┐
        │      Azure Portal               │
        └──────────────┬──────────────────┘
                       │
        ┌──────────────▼───────────────────┐
        │   Resource Group: rg-technova   │
        │                                 │
        │  ┌─────────────────────────┐   │
        │  │ App Service Plan (Free) │   │
        │  │ asp-technova            │   │
        │  └────────────┬────────────┘   │
        │               │                │
        │  ┌────────────▼────────────┐   │
        │  │ Web App                 │   │
        │  │ technova.azurewebsites  │   │
        │  │ .net                    │   │
        │  └────────────┬────────────┘   │
        │               │                │
        │  ┌────────────▼────────────┐   │
        │  │ Virtual Network         │   │
        │  │ vnet-technova           │   │
        │  │ └─ Subnet: 10.0.1.0/24 │   │
        │  └────────────────────────┘   │
        │                                 │
        │  ┌─────────────────────────┐   │
        │  │ Network Security Group  │   │
        │  │ └─ Allow HTTP (80)      │   │
        │  │ └─ Allow HTTPS (443)    │   │
        │  └─────────────────────────┘   │
        │                                 │
        └─────────────────────────────────┘
```

**Qué incluir:**
- 6 cajas principales + subelementos
- Jerarquía clara
- 4-5 colores

---

### 3️⃣ ESTRUCTURA DEL SITIO WEB
**Tiempo: 15 minutos**

```
            ┌─────────────────────────────┐
            │  TECHNOVA SOLUTIONS         │
            └────────────┬────────────────┘
                         │
            ┌────────────▼────────────┐
            │       NAVBAR            │
            │ Logo | Menu | Hamburger │
            └────────────┬────────────┘
                         │
        ┌────┬────────┬──────┬────────┐
        ▼    ▼        ▼      ▼        ▼
     HERO SERVICIOS NOSOTROS CONTACTO FOOTER
      │      │        │       │       │
      │    ┌─┼─┐      │     ┌─┴─┐    │
      │    ▼ ▼ ▼      ▼     ▼   ▼    │
      │   Web Mob Cloud Mis Vis Val   │
      │   Dev Apps Cloud Stat Data    │
      │   Etc                         │
```

**Qué incluir:**
- 6 secciones principales
- Subsecciones expandidas
- 6 colores diferentes

---

### 4️⃣ FLUJO DE USUARIO
**Tiempo: 20 minutos**

```
              ┌──────────────────┐
              │ Accede al sitio  │
              └────────┬─────────┘
                       │
              ┌────────▼────────┐
              │ ¿Dispositivo?   │
              └────┬─────────┬──┘
                   │         │
              Desktop    Mobile
                   │         │
              ┌────▼─────────▼──┐
              │ Explora página  │
              └────────┬────────┘
                       │
              ┌────────▼────────┐
              │ ¿Qué hace?      │
              └─┬────┬────┬────┬┘
                │    │    │    │
            Nav Lee Desc Contact
                │    │    │    │
              ┌─▼────▼────▼────▼─┐
              │ Interacción      │
              └─────────┬────────┘
                        │
              ┌─────────▼────────┐
              │ Envía formulario?│
              └────┬──────────┬──┘
                Sí          No
                │            │
            ┌───▼───┐   ┌────▼──┐
            │Gracias│   │ Cierra│
            └───────┘   └───────┘
```

**Qué incluir:**
- Inicio (círculo/rectángulo)
- Decisiones (rombos)
- Procesos (rectángulos)
- Fin (círculo)
- 4-5 colores

---

## 🎨 PALETA DE COLORES

Copia estos códigos directamente:

```
#0078D4 - Azul Principal
#4CAF50 - Verde
#FF6F00 - Naranja
#7B1FA2 - Púrpura
#C62828 - Rojo
#455A64 - Gris
```

---

## 🔧 PASOS PARA CREAR EN DRAW.IO

### Paso 1: Abre Draw.io
```
1. Ve a https://app.diagrams.net/
2. Click "Create New Diagram"
3. Elige "Blank Diagram"
```

### Paso 2: Inserta tu primer elemento
```
1. Left panel → search "rectangle"
2. Arrastra al canvas
3. Doble clic para agregar texto
4. Escribe nombre del elemento
```

### Paso 3: Agrega más elementos
```
1. Repite Paso 2 tantas veces como necesites
2. Coloca donde irán (no necesita alineación perfecta)
```

### Paso 4: Cambia colores
```
1. Click en forma
2. Right panel → "Format"
3. "Fill" → Selecciona color
4. O escribe código hex: #0078D4
```

### Paso 5: Conecta elementos
```
1. Click en forma A
2. Arrastra línea azul (punto) a forma B
3. Automáticamente se conectan
4. Doble clic en línea para agregar etiqueta
```

### Paso 6: Alinea todo (opcional)
```
1. Ctrl+A para seleccionar todo
2. Arrange → Align → tu opción
3. O arrastra manualmente
```

### Paso 7: Guarda
```
1. Ctrl+S o File → Save
2. Nombre: DIAGRAMA_ARQUITECTURA
3. Formato: .drawio (automático)
```

### Paso 8: Exporta
```
1. File → Export As
2. Elige: PNG (web) o PDF (imprimir)
3. Descarga archivo
```

---

## ✅ CHECKLIST RÁPIDO

### Antes de Exportar Cada Diagrama:

```
DIAGRAMA 1 - ARQUITECTURA:
□ 8 elementos
□ 6 colores diferentes
□ Todo etiquetado
□ Líneas limpias
□ Se entiende flujo
□ Exportado como PNG/PDF

DIAGRAMA 2 - INFRAESTRUCTURA:
□ Jerarquía clara
□ Resource Group visible
□ Todos servicios presentes
□ Reglas de seguridad mostradas
□ Se ve profesional
□ Exportado como PNG/PDF

DIAGRAMA 3 - ESTRUCTURA WEB:
□ 6 secciones principales
□ Subsecciones expandidas
□ Colores consistentes
□ Flujo de arriba a abajo
□ Footer incluido
□ Exportado como PNG/PDF

DIAGRAMA 4 - FLUJO USUARIO:
□ Inicio y fin claros
□ Decisiones con rombos
□ Caminos alternativos
□ Etiquetas en flechas
□ Se entiende journey
□ Exportado como PNG/PDF
```

---

## 📥 FORMATO DE EXPORTACIÓN RECOMENDADO

```
PARA PRESENTACIÓN:
→ PNG (1920x1080)
→ PDF (para imprimir)

PARA DOCUMENTACIÓN:
→ PDF (archivo permanente)
→ PNG (para web)

PARA COMPARTIR:
→ XML (formato nativo)
→ PDF (universal)

PARA AUDITORÍA:
→ VSDX (Visio compatibilidad)
→ PDF (sin cambios)
```

---

## ⏱️ TIEMPO TOTAL ESTIMADO

```
Diagrama 1: 15 min
Diagrama 2: 20 min
Diagrama 3: 15 min
Diagrama 4: 20 min
─────────────────
TOTAL:     70 min ≈ 1.5 horas
```

**Con experiencia previa: 30-45 minutos**

---

## 🆘 PROBLEMAS COMUNES

| Problema | Solución |
|----------|----------|
| No puedo conectar | Arrastra círculo azul entre formas |
| Texto muy pequeño | Right panel → Font size → 12pt mínimo |
| Colores no se ven | Usa códigos hex: #0078D4 |
| No se alinea | Ctrl+A → Arrange → Align |
| Archivo no guarda | File → Save / Ctrl+S |
| No puedo exportar | File → Export As → Selecciona formato |

---

## 🎯 PRÓXIMOS PASOS

```
1. AHORA: Abre https://app.diagrams.net/
2. YA: Crea "New Diagram"
3. HOY: Termina DIAGRAMA 1 (Arquitectura)
4. MAÑANA: Termina DIAGRAMAS 2-4
5. PRÓXIMA SEMANA: Integra en presentación
```

---

## 💪 ¡ADELANTE!

**Tienes:**
✅ Herramientas gratuitas
✅ Instrucciones paso a paso
✅ Paleta de colores lista
✅ Ejemplos y templates
✅ Todo lo necesario

**Ahora solo necesitas:**
⏰ 1.5 horas de tu tiempo
🎨 Creatividad
📐 Paciencia

**¡Vamos a hacerlo! 🚀**

---

## 📞 SI NECESITAS AYUDA

**Consulta estos archivos en tu carpeta:**
- `INFORMACION_CREAR_DIAGRAMAS.md` - Detalles completos
- `TUTORIALES_Y_RECURSOS.md` - Videos y recursos
- `COMPARATIVA_HERRAMIENTAS_DIAGRAMAS.md` - Todas las opciones
- `GUIA_DIAGRAMAS.md` - Guía general

**O busca:**
- "Draw.io tutorial español" en YouTube
- Comunidad: https://github.com/jgraph/drawio/discussions

---

**¡Éxito en tus diagramas! 🎉**
