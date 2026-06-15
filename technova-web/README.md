# TechNova Solutions - Sitio Web Corporativo

![Azure](https://img.shields.io/badge/Azure-App_Service-0078D4?logo=microsoft-azure)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

## 📋 Descripción

Sitio web corporativo profesional para **TechNova Solutions**, una empresa emergente de soluciones tecnológicas. El proyecto implementa un sitio web moderno, responsivo y completamente funcional alojado en **Microsoft Azure App Service**.

## ✨ Características

### 🎨 Diseño Profesional
- **Interfaz moderna** con gradientes y animaciones suaves
- **Totalmente responsivo** (mobile, tablet, desktop)
- **Accesibilidad** mejorada con iconos y navegación clara
- **Paleta de colores profesional** (azul y cyan)

### 📱 Responsive Design
- Se adapta perfectamente a cualquier dispositivo
- Menú móvil hamburguesa para pantallas pequeñas
- Optimizado para velocidad y rendimiento

### 🌐 Secciones del Sitio

#### 1. **Inicio (Hero Section)**
- Presentación llamativa con gradiente dinámico
- Llamada a la acción (CTA) destacada
- Animación de elemento flotante

#### 2. **Servicios**
Descripción de 3 servicios principales:
- **Desarrollo Web**: Sitios modernos y responsivos
- **Aplicaciones Móviles**: Apps nativas e híbridas
- **Consultoría Cloud**: Migración y optimización

Cada servicio incluye:
- Ícono representativo
- Descripción detallada
- Lista de características

#### 3. **Nosotros**
- Información sobre la empresa
- **Misión**: Impulsar crecimiento digital
- **Visión**: Ser la empresa preferida
- **Valores**: Integridad, innovación, excelencia
- **Estadísticas**: 25+ proyectos, 15+ clientes, 8 profesionales

#### 4. **Contacto**
- Información de contacto directa
- **Dirección, teléfono, email**
- Enlaces a redes sociales
- **Formulario de contacto funcional** con validación
- Notificaciones de éxito/error

### 🎯 Funcionalidades JavaScript
- ✅ Menú móvil interactivo
- ✅ Navegación suave entre secciones
- ✅ Validación de formulario
- ✅ Notificaciones visuales
- ✅ Animaciones al desplazarse (scroll)
- ✅ Contadores animados en estadísticas
- ✅ Efectos hover en elementos interactivos

## 📁 Estructura de Archivos

```
technova-web/
├── index.html              # Página principal
├── css/
│   └── styles.css         # Estilos (3000+ líneas profesionales)
├── js/
│   └── script.js          # Lógica interactiva
└── assets/                # Carpeta para imágenes futuras
```

## 🚀 Tecnologías Utilizadas

- **HTML5**: Estructura semántica moderna
- **CSS3**: Grid, Flexbox, animaciones, gradientes
- **JavaScript Vanilla**: Sin dependencias externas
- **Font Awesome 6.4**: Iconografía profesional
- **Azure App Service**: Hosting en la nube

## 📊 Especificaciones Técnicas

### Diseño Responsivo
- **Breakpoints**:
  - Desktop: 1200px+
  - Tablet: 769px - 1200px
  - Mobile: 480px - 768px
  - Small Mobile: <480px

### Performance
- Carga rápida sin dependencias pesadas
- CSS optimizado y minificable
- JavaScript eficiente sin frameworks
- Imágenes vectoriales (iconos SVG)

### Accesibilidad
- Navegación clara y lógica
- Contraste de colores adecuado
- Iconos con etiquetas descriptivas
- Formulario con validación

## 🎯 Requisitos del Proyecto

✅ **Infraestructura Azure**
- Resource Group: `rg-technova`
- Virtual Network: `vnet-technova`
- Subnet: `subnet-app`
- NSG: `nsg-technova`
- App Service Plan: `asp-technova` (Free tier)
- Web App: `technova`

✅ **Seguridad**
- VNet Integration configurada
- NSG con reglas HTTP/HTTPS
- Access Restrictions habilitadas

✅ **Sitio Web**
- HTML5 semántico
- CSS3 moderno
- JavaScript interactivo
- Responsivo en todas las plataformas

## 🌍 Despliegue en Azure

### Pasos Rápidos

1. **Preparar recursos Azure**
   - Crear Resource Group
   - Crear VNet y Subnet
   - Crear NSG con reglas
   - Crear App Service Plan (Free)
   - Crear Web App

2. **Integrar VNet**
   - Habilitar VNet Integration
   - Asociar NSG a Subnet

3. **Desplegar sitio**
   - Subir archivos a Azure
   - Verificar en URL pública

4. **Validar**
   - Acceder a `https://technova.azurewebsites.net`
   - Probar todas las secciones

**Ver guía completa en: `GUIA_IMPLEMENTACION_AZURE.md`**

## 💰 Costos Estimados

- **App Service (Free tier)**: $0/mes
- **VNet**: $0/mes
- **NSG**: $0/mes
- **Total con Azure for Students**: $0/mes

## 🎨 Personalización

Puedes customizar fácilmente:

### Colores
En `css/styles.css`, modifica las variables CSS:
```css
--primary-color: #0066ff;    /* Azul principal */
--secondary-color: #00d4ff;  /* Cyan */
--dark-color: #0f1419;       /* Oscuro */
```

### Contenido
En `index.html`:
- Cambia textos y descripciones
- Actualiza información de contacto
- Modifica nombres de servicios

### Imagen/Logo
Reemplaza el ícono `<i class="fas fa-rocket"></i>` con tu logotipo

## 📱 Compatibilidad

- ✅ Chrome (últimas versiones)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Navegadores móviles

## 🔍 SEO Básico

- Meta tags configurados
- Títulos descriptivos
- Estructura semántica
- Velocidad de carga optimizada

## 📞 Información de Contacto

**TechNova Solutions**
- 📍 Calle Principal 123, San Salvador, El Salvador
- 📞 +503 2345-6789
- 📧 info@technova.com
- 🌐 https://technova.azurewebsites.net

## 📚 Documentación Adicional

- [Guía de Implementación en Azure](./GUIA_IMPLEMENTACION_AZURE.md)
- [Documentación Azure App Service](https://docs.microsoft.com/azure/app-service/)
- [Documentación Azure Networking](https://docs.microsoft.com/azure/virtual-network/)

## ✍️ Autor

Proyecto desarrollado para fines educativos.

## 📄 Licencia

Este proyecto es código abierto y puede ser utilizado libremente con fines educativos y comerciales.

---

## 🚀 Próximos Pasos

1. **Desplegar en Azure** (ver guía)
2. **Personalizar contenido** con información real
3. **Agregar dominio personalizado**
4. **Implementar Analytics**
5. **Mejorar SEO**
6. **Agregar más funcionalidades**

---

**¡Sitio TechNova Solutions listo para producción! 🎉**

Última actualización: Junio 2024
