# 📐 INFORMACIÓN DETALLADA PARA CREAR LOS DIAGRAMAS

## Guía Paso a Paso para Crear tus Propios Diagramas

---

## 1️⃣ DIAGRAMA DE ARQUITECTURA

### Estructura:
```
Nivel 1 (Arriba):
├─ Navegador Web (Usuario)

Nivel 2 (Centro):
├─ Azure App Service
├─ CDN FontAwesome

Nivel 3 (Componentes):
├─ index.html
├─ css/styles.css
├─ js/script.js
├─ assets/imágenes

Nivel 4 (Secciones):
├─ Hero/Inicio
├─ Servicios
├─ Nosotros
├─ Contacto
```

### Elementos a Incluir:

| Elemento | Forma | Color | Descripción |
|----------|-------|-------|------------|
| Navegador Web | Rectángulo | #E1F5FF (Azul claro) | Usuario final |
| Azure App Service | Rectángulo | #0078D4 (Azul) | Servidor principal |
| index.html | Rectángulo | #FFF9C4 (Amarillo) | Página HTML |
| CSS | Rectángulo | #C8E6C9 (Verde) | Estilos |
| JavaScript | Rectángulo | #F8BBD0 (Rosa) | Interactividad |
| Assets | Rectángulo | #B2DFDB (Turquesa) | Recursos |
| CDN | Rectángulo | #FFE0B2 (Naranja claro) | Fuente externa |
| Secciones | Rectángulo | #E1BEE7 (Púrpura) | Contenido web |

### Conexiones:
```
Usuario → App Service
    ↓
App Service → HTML
    ↓
HTML → CSS
HTML → JavaScript  
HTML → Assets
    ↓
HTML → Secciones Web
    ↓
Secciones (Hero, Servicios, Nosotros, Contacto)
```

### Pasos en Draw.io:
1. **Crear**: Arrastra rectángulo 8 veces
2. **Textos**: Doble clic en cada forma
3. **Colores**: Click derecho → Format → Fill
4. **Conectar**: Arrastra línea de un elemento a otro
5. **Alinear**: Ctrl+A → Arrange → Align

---

## 2️⃣ DIAGRAMA DE INFRAESTRUCTURA AZURE

### Jerarquía:
```
Azure Portal
    ↓
Resource Group: rg-technova
    ├─ App Service Plan: asp-technova (Free Tier)
    ├─ Web App: technova (azurewebsites.net)
    ├─ Virtual Network: vnet-technova
    │   └─ Subnet: subnet-app (10.0.1.0/24)
    └─ Network Security Group: nsg-technova
        ├─ Regla: Allow HTTP (80)
        └─ Regla: Allow HTTPS (443)
```

### Elementos Principales:

| Elemento | Forma | Color | Ubicación |
|----------|-------|-------|-----------|
| Azure Portal | Rectángulo | #0078D4 | Arriba |
| Resource Group | Rectángulo | #0078D4 | Centro arriba |
| App Service Plan | Rectángulo | #4CAF50 | Centro |
| Web App | Rectángulo | #4CAF50 | Centro |
| Virtual Network | Rectángulo | #1E88E5 | Centro derecha |
| Network Security Group | Rectángulo | #FF6F00 | Derecha |
| Subnet | Rectángulo | #B3E5FC | Abajo |
| Reglas HTTP/HTTPS | Rectángulo | #FFCCBC | Abajo derecha |
| Static Content | Rectángulo | #C8E6C9 | Centro abajo |
| Usuarios | Rectángulo | #FF9800 | Arriba izquierda |

### Conexiones:
```
Usuarios → Internet → Web App
    ↓
Resource Group contiene:
    - App Service Plan → Web App
    - Virtual Network → Subnet
    - NSG → Reglas (HTTP/HTTPS)
    ↓
Web App aloja Static Content
```

---

## 3️⃣ DIAGRAMA DE ESTRUCTURA DEL SITIO WEB

### Jerarquía Visual:
```
TECHNOVA SOLUTIONS (Centro superior)
    ↓
NAVBAR (Menú de navegación)
    ↓
┌─────────────────────────────────────┐
│ HERO         SERVICIOS  NOSOTROS   CONTACTO │
│ (Portada)    (Descripción)(Equipo) (Formulario)│
└─────────────────────────────────────┘
    ↓
FOOTER (Pie de página)
```

### Secciones Detalladas:

**NAVBAR:**
- Logo + Nombre
- Menú: Inicio, Servicios, Nosotros, Contacto
- Hamburger menu (para móvil)

**HERO SECTION:**
- Título principal
- Subtítulo
- Botón CTA (Empieza Hoy)
- Imagen/Fondo

**SERVICIOS:**
- 🌐 Desarrollo Web
  - Sitios modernos
  - Responsivos
  - Rápidos
  
- 📱 Aplicaciones Móviles
  - Apps nativas
  - Híbridas
  - Multiplataforma
  
- ☁️ Consultoría Cloud
  - Migración
  - Optimización
  - Seguridad

**NOSOTROS:**
- Misión
- Visión
- Valores
- Estadísticas:
  - 25+ Proyectos
  - 15+ Clientes
  - 8 Profesionales

**CONTACTO:**
- Formulario con:
  - Nombre (text input)
  - Email (email input)
  - Mensaje (textarea)
  - Botón Enviar
  
**FOOTER:**
- Copyright
- Enlaces útiles
- Redes sociales
- Contacto

### Elementos Visuales:

| Sección | Color Fondo | Ícono | Descripción |
|---------|-------------|-------|------------|
| NAVBAR | #1E88E5 | 🔝 | Navegación |
| HERO | #FF6F00 | 🎨 | Portada |
| SERVICIOS | #388E3C | 💼 | 3 servicios |
| NOSOTROS | #7B1FA2 | 👥 | Datos empresa |
| CONTACTO | #C62828 | 📧 | Formulario |
| FOOTER | #455A64 | © | Pie de página |

---

## 4️⃣ DIAGRAMA DE FLUJO DE USUARIO

### Path Principal:

```
INGRESO
   ↓
¿En qué dispositivo?
   ├─ Desktop → Versión Completa
   └─ Mobile  → Versión Responsiva
   ↓
EXPLORACIÓN
   ├─ Lee Hero Section
   ├─ Descubre Servicios
   ├─ Aprende sobre Nosotros
   └─ Accede a Contacto
   ↓
INTERACCIÓN
   ├─ Navega: Menú principal
   ├─ Lee: Contenido
   ├─ Descubre: Servicios
   ├─ Aprende: Info empresa
   └─ Contacta: Formulario
   ↓
ACCIÓN FINAL
   ├─ Envía mensaje (contacto)
   ├─ Vuelve a inicio
   └─ Cierra pestaña
```

### Decisiones (Rombos):

1. **¿Dispositivo?**
   - Sí Desktop → Versión Escritorio
   - Sí Mobile → Versión Móvil

2. **¿Qué hace?**
   - Navega
   - Lee contenido
   - Descubre servicios
   - Aprende info
   - Contacta

3. **¿Envía formulario?**
   - Sí → Confirmación
   - No → Cierra

### Elementos Gráficos:

```
Inicio (Círculo/Rectángulo redondeado)
   ↓
Decisión (Rombo)
   ↓
Procesos (Rectángulo)
   ↓
Final (Círculo/Rectángulo redondeado)
```

### Colores por Estado:

| Estado | Color |
|--------|-------|
| Inicio | Verde (#4CAF50) |
| Decisión | Amarillo (#FFC107) |
| Acción | Azul (#2196F3) |
| Final | Rojo (#C62828) |
| Error | Gris (#757575) |

---

## 🎨 PALETA DE COLORES CORPORATIVA TECHNOVA

```
COLORES PRINCIPALES:
├─ Azul Principal: #0078D4 (Logo, Headers)
├─ Azul Oscuro: #003d99 (Bordes, Énfasis)
├─ Verde Acento: #4CAF50 (Botones positivos)
├─ Naranja: #FF6F00 (Alertas, Destacados)
├─ Púrpura: #7B1FA2 (Servicios, Secundario)
└─ Gris: #455A64 (Footer, Texto)

COLORES CLAROS (Para fondos):
├─ Azul Claro: #E1F5FF
├─ Verde Claro: #C8E6C9
├─ Naranja Claro: #FFE0B2
├─ Púrpura Claro: #E1BEE7
└─ Gris Claro: #ECEFF1
```

---

## 📏 PROPORCIONES RECOMENDADAS

### Tamaño de Formas:

```
Elementos principales: 150 x 70 px
Elementos secundarios: 120 x 50 px
Elementos pequeños: 100 x 40 px
Conectores: 2-3 px grosor
```

### Espaciado:

```
Horizontal: 50-100 px entre elementos
Vertical: 80-150 px entre niveles
Márgenes: 50 px desde bordes
```

---

## ✅ CHECKLIST PARA CADA DIAGRAMA

### Antes de Exportar:

- [ ] Todos los elementos etiquetados
- [ ] Colores consistentes
- [ ] Líneas de conexión claras
- [ ] Texto legible (mínimo 10pt)
- [ ] Centrado en la página
- [ ] Sin elementos superpuestos innecesariamente
- [ ] Leyenda o referencias si es necesario
- [ ] Título del diagrama visible
- [ ] Versión y fecha (opcional)

---

## 🛠️ HERRAMIENTAS: PASOS ESPECÍFICOS

### CREAR EN DRAW.IO:

**Paso 1: Abrir**
```
1. Ve a app.diagrams.net
2. Click "Create New Diagram"
3. Elige "Blank Diagram"
```

**Paso 2: Insertar Formas**
```
1. Panel izquierdo: Busca "Rectangle"
2. Arrastra al canvas
3. Repite para todos los elementos
```

**Paso 3: Agregar Texto**
```
1. Doble clic en forma
2. Escribe el texto
3. Click fuera para terminar
```

**Paso 4: Cambiar Colores**
```
1. Click en forma
2. Panel derecho: "Format"
3. "Fill" → Color deseado
4. "Stroke" → Color borde
```

**Paso 5: Conectar**
```
1. Click en forma origen
2. Arrastra línea azul a destino
3. Doble clic para etiquetar conexión
```

**Paso 6: Guardar**
```
File → Save As → Nombre.drawio
```

**Paso 7: Exportar**
```
File → Export As → 
  • PNG (para web)
  • PDF (para imprimir)
  • SVG (para editar después)
```

---

### CREAR EN VISIO:

**Paso 1: Abrir**
```
1. Microsoft Visio
2. File → New → Blank Document
```

**Paso 2: Insertar Formas**
```
1. Right panel: "Shapes"
2. Busca "Rectangles"
3. Arrastra formas
```

**Paso 3: Personalizar**
```
1. Right-click forma → Format Shape
2. Fill → Color
3. Line → Tipo de línea
```

**Paso 4: Conectar**
```
1. Menú "Connector" en ribbon
2. Dibuja línea entre formas
```

**Paso 5: Guardar**
```
File → Save As → Nombre.vsdx
```

---

### CREAR EN LUCIDCHART:

**Paso 1: Abrir**
```
1. lucidchart.com
2. "+ New document"
3. "Blank Diagram"
```

**Paso 2: Insertar Formas**
```
1. Left panel: "Shapes"
2. Busca categoría
3. Arrastra al canvas
```

**Paso 3: Propiedades**
```
1. Click forma → Right panel
2. "Appearance" → Color
3. "Data" → Etiqueta
```

**Paso 4: Colaborar**
```
1. Top right: "Share"
2. Invita colaboradores
3. Edición en tiempo real
```

**Paso 5: Exportar**
```
Top menu: "Download"
→ PNG, PDF, SVG, VSDX
```

---

## 📋 TEMPLATE PARA DOCUMENTAR DIAGRAMAS

```
NOMBRE DIAGRAMA: ___________________
FECHA: ___________________
VERSIÓN: ___________________
RESPONSABLE: ___________________

PROPÓSITO:
[Describe qué muestra este diagrama]

ELEMENTOS PRINCIPALES:
- [Elemento 1]: [Descripción]
- [Elemento 2]: [Descripción]
- [Elemento 3]: [Descripción]

FLUJO:
[Describe cómo se lee el diagrama]

NOTAS:
[Observaciones adicionales]

CAMBIOS REALIZADOS:
v1.0 - Versión inicial
v1.1 - [Cambios]
```

---

## 🎯 PRÓXIMOS PASOS

1. **Elige herramienta**: Draw.io (más fácil), Visio (profesional), Lucidchart (colaborativo)
2. **Descarga informacion**: Usa esta guía como referencia
3. **Crea primer diagrama**: Comienza con Arquitectura
4. **Personaliza**: Colores, textos, proporcioness
5. **Exporta**: PNG/PDF para presentar
6. **Comparte**: Con tu equipo

---

## 🔗 RECURSOS RÁPIDOS

- **Draw.io**: https://app.diagrams.net/
- **Visio**: https://www.microsoft.com/visio/
- **Lucidchart**: https://www.lucidchart.com/
- **Iconos**: https://fonts.google.com/icons/
- **Colores**: https://coolors.co/

---

**¡Tienes toda la información para crear tus diagramas profesionales! 💪**
