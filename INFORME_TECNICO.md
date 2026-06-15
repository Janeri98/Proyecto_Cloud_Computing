# INFORME TÉCNICO

## Proyecto: Publicación de un Sitio Web Corporativo en Microsoft Azure App Service

### Autor: TechNova Solutions (Proyecto Educativo)
### Fecha: Junio 2026

---

## 1. Introducción

El presente informe técnico describe el desarrollo e implementación de un sitio web corporativo para la empresa ficticia **TechNova Solutions**, utilizando servicios de Microsoft Azure, en particular **Azure App Service**. El objetivo principal fue crear una solución de bajo costo, confiable y profesional que permita presentar la información institucional, los servicios ofrecidos, contactos y una breve descripción de proyectos relevantes.

El proyecto se diseñó con un enfoque en **PaaS (Platform as a Service)**, aprovechando los beneficios de la infraestructura administrada por Azure para obtener una implementación rápida, segura y escalable.

---

## 2. Objetivo del Proyecto

### 2.1 Objetivo General

Diseñar e implementar un sitio web corporativo utilizando Microsoft Azure App Service, aplicando conceptos fundamentales de computación en la nube, servicios PaaS, seguridad básica y administración de recursos en Azure.

### 2.2 Objetivos Específicos

- Crear un sitio web con diseño profesional, responsivo y funcional.
- Implementar la infraestructura necesaria en Azure con recursos económicos y gratuitos.
- Configurar una red virtual (VNet) y reglas de seguridad para proteger la aplicación.
- Desplegar el sitio en un **App Service Plan** gratuito y conectar el servicio a la red virtual.
- Documentar todo el proceso para facilitar la evaluación y futura entrega.

---

## 3. Caso de Negocio: TechNova Solutions

TechNova Solutions es una empresa emergente dedicada al desarrollo de soluciones tecnológicas para pequeñas y medianas empresas. El objetivo del sitio web era reflejar una imagen corporativa profesional y accesible, destacando los servicios principales, valores de la empresa y canales de contacto.

### 3.1 Requerimientos del Cliente

Los requisitos mínimos establecidos fueron:

- Presentar información institucional.
- Describir los servicios ofrecidos.
- Incluir una sección "Nosotros" con misión, visión y valores.
- Incluir un formulario de contacto.
- Publicar el sitio en Microsoft Azure con costos reducidos.
- Implementar seguridad básica y administración de recursos en Azure.

### 3.2 Propuesta de Valor

Se propuso un sitio web estático, moderno y adaptable que permitiera a la empresa lograr una presencia digital confiable sin incurrir en costos elevados. Al alojar el sitio en **Azure App Service Free Tier**, la solución mantiene un presupuesto controlado y aprovecha la infraestructura administrada de Azure.

---

## 4. Arquitectura de la Solución

La solución se basa en una arquitectura simple pero efectiva:

- **Cliente**: Navegador web que consume contenido estático.
- **Hosting**: Azure App Service (Web App) con contenido HTML/CSS/JS.
- **Red**: Virtual Network (VNet) y Subnet dedicada.
- **Seguridad**: Network Security Group (NSG) y reglas de acceso.
- **Despliegue**: Archivos estáticos subidos directamente a Azure o mediante Git/ZIP.

### 4.1 Diagrama Conceptual

```
Usuario --> Azure App Service --> Contenido estático (HTML/CSS/JS)
                 │
                 ├── VNet Integration
                 │
                 └── NSG con reglas HTTP/HTTPS
```

### 4.2 Componentes Principales

- **Resource Group**: Contenedor principal de todos los recursos.
- **Virtual Network (`vnet-technova`)**: Red privada para conectar servicios.
- **Subnet (`subnet-app`)**: Subred dedicada para la integración del App Service.
- **Network Security Group (`nsg-technova`)**: Control de tráfico entrante.
- **App Service Plan (`asp-technova`)**: Plan de hospedaje en Free Tier.
- **Web App (`technova`)**: Aplicación web que sirve el sitio.

---

## 5. Desarrollo del Sitio Web

### 5.1 Tecnologías Utilizadas

- **HTML5**: Estructura semántica de la página.
- **CSS3**: Estilos modernos, diseño responsivo, animaciones y gradientes.
- **JavaScript Vanilla**: Interactividad sin dependencias externas.
- **Font Awesome**: Iconografía profesional.

### 5.2 Contenido Principal

El sitio contiene las siguientes secciones:

- **Inicio**: Nombre de la empresa, logotipo, descripción general y llamada a la acción.
- **Servicios**: Descripción de tres servicios tecnológicos principales.
- **Nosotros**: Misión, visión, valores y estadísticas de la empresa.
- **Contacto**: Información de contacto, redes sociales y formulario visual.
- **Footer**: Información de derechos y referencia a Azure App Service.

### 5.3 Diseño y Experiencia de Usuario

El diseño se orientó a un estilo corporativo moderno y atractivo, con colores azules y cyan, un menú fijo y animaciones suaves. La experiencia incluye:

- Navegación suave entre secciones.
- Menú "hamburguesa" para dispositivos móviles.
- Feedback visual para el envío del formulario.
- Elementos animados al hacer scroll.

### 5.4 Estructura de Archivos

```
technova-web/
├── index.html
├── css/styles.css
├── js/script.js
└── web.config
```

---

## 6. Configuración de Azure

### 6.1 Suscripción y Costos

Se utilizó una suscripción gratuita o equivalente, buscando mantener el costo mensual en **$0** mediante el uso del **Free Tier** y, de ser necesario, créditos de **Azure for Students**.

### 6.2 Resource Group

- Nombre: `rg-technova`
- Descripción: Agrupa todos los recursos del proyecto.

### 6.3 App Service Plan

- Nombre: `asp-technova`
- Tipo: Free Tier (F1)
- Sistema operativo: Windows
- Propósito: Hospedar la Web App sin costos adicionales.

### 6.4 Azure App Service

- Nombre de la Web App: `technova`
- Runtime: Contenido estático HTML/CSS/JS
- URL pública esperada: `https://technova.azurewebsites.net`

### 6.5 Virtual Network y Subnet

- Nombre de la VNet: `vnet-technova`
- Rango IPv4: `10.0.0.0/16`
- Nombre de la Subnet: `subnet-app`
- Rango de Subnet: `10.0.1.0/24`

### 6.6 Integración de Red

- Se habilitó **VNet Integration** en la Web App.
- La aplicación puede comunicarse de forma privada con la red virtual.

---

## 7. Seguridad y Control de Acceso

### 7.1 Network Security Group

Se creó un NSG con reglas básicas para proteger la subred:

- Permitir tráfico HTTP en puerto 80.
- Permitir tráfico HTTPS en puerto 443.
- Denegar puertos no necesarios.

### 7.2 Reglas de Restricción de Acceso

Se configuraron restricciones en el App Service para permitir el acceso solo a rangos de IP específicos o a la VNet según el requerimiento.

### 7.3 Configuración Adicional de Seguridad

Se incluyeron cabeceras de seguridad en el archivo `web.config`, tales como:

- X-Content-Type-Options: nosniff.
- X-Frame-Options: SAMEORIGIN.
- X-XSS-Protection: 1; mode=block.
- Referrer-Policy: strict-origin-when-cross-origin.
- Content-Security-Policy para limitar orígenes de scripts y estilos.

---

## 8. Proceso de Despliegue

### 8.1 Métodos de Despliegue

Se consideraron las siguientes opciones:

- **Azure Portal**: despliegue manual o Local Git.
- **Git**: configuración de repositorio y push a Azure.
- **ZIP deployment**: carga directa de un archivo comprimido.
- **Kudu Console**: subida de archivos directamente al directorio `/site/wwwroot`.

### 8.2 Pasos Seguidos

1. Crear todos los recursos en Azure.
2. Habilitar la integración de la Web App con la VNet.
3. Subir los archivos del sitio al directorio de publicación.
4. Verificar que el contenido estático se sirve correctamente.
5. Validar la funcionalidad de los enlaces, el menú y el formulario.

### 8.3 Verificación Final

- Acceso a la URL pública de la Web App.
- Carga correcta de HTML, CSS y JavaScript.
- Navegación responsiva en diferentes dispositivos.
- Ausencia de errores en consola de navegador.
- Validación del formulario y mensajes de retroalimentación.

---

## 9. Resultados Obtenidos

### 9.1 Sitio Web

Se implementó exitosamente un sitio web estático que incluye:

- Presentación institucional clara.
- Descripción de servicios tecnológicos.
- Sección de "Nosotros" con misión, visión y valores.
- Formulario de contacto funcional.
- Estilo visual corporativo y responsivo.

### 9.2 Infraestructura en Azure

Los recursos creados en Azure cumplen con los requisitos del proyecto y se configuraron para minimizar costos.

### 9.3 Seguridad

La solución integra controles de acceso y seguridad básica, incluyendo el uso de un NSG y reglas de cabeceras de seguridad.

### 9.4 Documentación

Se generó amplia documentación de soporte, incluyendo guías, checklist y resúmenes que facilitan la replicación y evaluación del proyecto.

---

## 10. Conclusiones

El proyecto demuestra cómo una empresa emergente puede publicar un sitio web corporativo moderno en Microsoft Azure utilizando servicios básicos y gratuitos. La arquitectura propuesta es eficiente, segura y económica.

El uso de **Azure App Service** permitió enfocarse en el diseño y contenido del sitio sin preocuparse por la administración de servidores. La integración con la VNet y las reglas de seguridad garantizan un nivel básico de protección adecuada para este tipo de implementación.

Además, la solución es escalable: en caso de requerir más capacidad, se puede migrar fácilmente a un plan superior en Azure sin cambiar el diseño del sitio.

---

## 11. Recomendaciones

Para una futura versión más avanzada del proyecto se recomienda:

- Implementar un backend ligero para manejo real de formularios.
- Conectar el sitio a una base de datos para almacenar contactos y solicitudes.
- Añadir un dominio personalizado.
- Usar certificados SSL personalizados cuando se requiera un dominio propio.
- Incluir análisis de tráfico con herramientas como Google Analytics o Azure Application Insights.
- Evaluar el uso de Azure CDN para mejorar la performance global.

---

## 12. Apéndice

### 12.1 Estructura de Archivos del Proyecto

```
technova-web/
├── index.html
├── css/styles.css
├── js/script.js
├── web.config
├── README.md
├── RESUMEN_EJECUTIVO.md
├── GUIA_IMPLEMENTACION_AZURE.md
├── CHECKLIST_IMPLEMENTACION.md
├── INDICE.md
├── PLAN_EJECUCION_RAPIDA.md
└── COMANDOS_UTILES.md
```

### 12.2 Recursos Azure Creado

- Resource Group: `rg-technova`
- Virtual Network: `vnet-technova`
- Subnet: `subnet-app`
- Network Security Group: `nsg-technova`
- App Service Plan: `asp-technova`
- Web App: `technova`

### 12.3 URL de Entrega

- URL pública esperada del sitio: `https://technova.azurewebsites.net`

---

## 13. Anexos

### 13.1 Resumen de Costos

El proyecto está diseñado para funcionar con costos mínimos:

- App Service Plan Free Tier: $0
- Virtual Network: $0
- NSG: $0
- Transferencia de datos dentro del nivel gratuito: $0

### 13.2 Indicadores de Éxito

- El sitio debe ser accesible desde un navegador.
- Todas las secciones deben mostrarse correctamente.
- El diseño debe adaptarse a pantallas móviles.
- El formulario debe validarse correctamente.
- La infraestructura debe estar configurada en Azure.

---

### Observaciones Generales

El proyecto cumple con los requisitos planteados por la institución educativa y ofrece un entregable completo que puede utilizarse como muestra de competencias en desarrollo web y administración de servicios cloud en Microsoft Azure.
