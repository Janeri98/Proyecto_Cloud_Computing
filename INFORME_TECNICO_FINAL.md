# INFORME TÉCNICO

## Proyecto: Publicación de un Sitio Web Corporativo en Microsoft Azure App Service

### Empresa: TechNova Solutions (Ficticia)
### Fecha: Junio 2026

---

## 1. Introducción

El presente informe técnico describe el desarrollo e implementación de un sitio web corporativo para la empresa ficticia **TechNova Solutions**, alojado en **Microsoft Azure App Service**. El proyecto tiene como objetivo demostrar la capacidad de una solución cloud para ofrecer presencia digital profesional, uso eficiente de recursos, seguridad básica y administración simplificada.

Este informe incluye la descripción del proyecto, los objetivos generales y específicos, la arquitectura implementada, la explicación de los servicios utilizados, la seguridad basada en HTTPS, una proyección de costos para ambientes de desarrollo y producción, las ventajas del modelo PaaS sobre la infraestructura tradicional, así como las conclusiones y las lecciones aprendidas.

---

## 2. Descripción del Proyecto

TechNova Solutions es una empresa emergente dedicada al desarrollo de soluciones tecnológicas para pequeñas y medianas empresas. El proyecto consistió en crear un sitio web corporativo que permita presentar la información institucional, los servicios ofrecidos, los valores de la empresa y un canal de contacto con los visitantes.

El sitio web fue desarrollado como una aplicación estática con tecnologías web front-end: **HTML5, CSS3 y JavaScript**. La solución se diseñó para tener un aspecto profesional, con un menú de navegación intuitivo, secciones claras y un diseño adaptable a dispositivos móviles.

El hospedaje se realizó en Azure App Service, utilizando un plan de bajo costo adecuado para la fase de desarrollo, y con una arquitectura que permite escalar según la demanda en producción.

### 2.1 Alcance

El alcance del proyecto incluye:

- Desarrollo del sitio web estático con secciones de Inicio, Servicios, Nosotros y Contacto.
- Creación de la infraestructura en Microsoft Azure:
  - Resource Group
  - App Service Plan
  - Azure App Service
  - Virtual Network y Subnet
  - Network Security Group
- Configuración de seguridad de acceso y cabeceras de seguridad.
- Documentación del proceso y generación de reportes técnicos.

### 2.2 Exclusiones

El proyecto no incluyó:

- Desarrollo de una capa de backend para procesamiento de datos.
- Base de datos para almacenamiento persistente.
- Integración con sistemas de pago o CRM.
- Funcionalidades dinámicas avanzadas.

---

## 3. Objetivos

### 3.1 Objetivo General

Diseñar e implementar un sitio web corporativo para TechNova Solutions utilizando Microsoft Azure App Service, aplicando conceptos de computación en la nube, servicios PaaS, seguridad básica y administración de recursos en Azure.

### 3.2 Objetivos Específicos

- Desarrollar un sitio web estático con diseño profesional y responsive.
- Configurar un **Resource Group** y un **App Service Plan** en Azure.
- Crear una **Virtual Network** y una **Subnet** dedicada para la integración del App Service.
- Implementar un **Network Security Group (NSG)** que permita tráfico HTTP/HTTPS y deniegue puertos no necesarios.
- Configurar restricciones de acceso y asegurar la aplicación con HTTPS.
- Documentar la implementación y proporcionar un informe técnico.

---

## 4. Arquitectura Implementada

### 4.1 Visión General de la Arquitectura

La arquitectura se basa en una solución PaaS que aprovecha los servicios administrados de Azure. El contenido estático del sitio se almacena y sirve desde un **Azure App Service**, mientras que la red se aísla y protege con una **Virtual Network** y un **NSG**.

### 4.2 Componentes de la Arquitectura

- **Resource Group**: Agrupa todos los recursos de Azure del proyecto.
- **Azure App Service**: Servicio principal encargado de hospedar y servir el sitio web.
- **App Service Plan**: Plan de hosting que define la capacidad de cómputo del App Service.
- **Virtual Network (VNet)**: Red privada que facilita la integración de servicios.
- **Subnet**: Segmento de red dedicado a la integración del App Service.
- **Network Security Group (NSG)**: Controla el tráfico entrante y saliente a la subred.

### 4.3 Flujo de la Solución

1. El usuario accede a la URL pública del sitio.
2. Azure App Service entrega los archivos HTML, CSS y JavaScript al navegador.
3. El App Service utiliza la VNet para comunicación privada interna cuando es necesario.
4. El NSG protege el acceso permitiendo solo HTTP y HTTPS.

### 4.4 Beneficios del Diseño

- Simplificación de la administración de infraestructura.
- Escalabilidad futura con planes superiores de App Service.
- Mejora en la seguridad al limitar el acceso de red.
- Menor tiempo de despliegue en comparación con una infraestructura tradicional.

---

## 5. Servicio Utilizado: Azure App Service

### 5.1 Descripción de Azure App Service

**Azure App Service** es una plataforma de aplicaciones en la nube que permite hospedar aplicaciones web, API y sitios estáticos sin tener que administrar servidores. Proporciona capacidades integradas como despliegue continuo, escalado automático, administración de certificados SSL y monitorización.

En este proyecto, se utilizó Azure App Service para hospedar un sitio web estático, aprovechando la facilidad de despliegue y el costo reducido en la fase de desarrollo.

### 5.2 Características relevantes del servicio

- **Despliegue rápido**: Permite subir contenido directamente o mediante repositorios Git.
- **Escalabilidad**: Soporta escalado vertical y horizontal según la demanda.
- **Integración con Azure VNet**: Permite comunicación segura entre servicios.
- **Certificados SSL**: Soporta HTTPS de forma nativa.
- **Administración simplificada**: El servicio gestiona la infraestructura subyacente.

### 5.3 Elección del plan de servicio

Para el ambiente de desarrollo se eligió un **App Service Plan Free Tier** que no incurre en costos mensuales. Este plan es adecuado para pruebas, demostraciones y etapas tempranas del proyecto.

Para un ambiente de producción con 1000 usuarios concurrentes se recomienda migrar a un plan **Standard o Premium** que ofrezca mayor capacidad y asistencia técnica.

---

## 6. Seguridad

### 6.1 HTTPS y sus beneficios

El protocolo **HTTPS** protege la comunicación entre el navegador del usuario y el servidor web mediante cifrado TLS. Esto evita que terceros intercepten, modifiquen o roben información transmitida.

#### Beneficios de HTTPS

- **Confidencialidad**: Los datos se transmiten cifrados.
- **Integridad**: Se detectan modificaciones no autorizadas en tránsito.
- **Autenticidad**: Los usuarios pueden verificar que acceden al sitio correcto.
- **Mejora SEO**: Los motores de búsqueda prefieren sitios con HTTPS.
- **Cumplimiento de buenas prácticas**: Es un estándar mínimo de seguridad en la web.

### 6.2 Implementación de seguridad en el proyecto

- **App Service**: Se habilitó HTTPS de forma predeterminada.
- **NSG**: Solo se permitieron los puertos 80 (HTTP) y 443 (HTTPS).
- **VNet Integration**: Se aisló la aplicación dentro de una red privada.
- **Cabeceras de seguridad**: Se incluyeron políticas como `X-Content-Type-Options`, `X-Frame-Options` y `Content-Security-Policy`.

### 6.3 Consideraciones adicionales

Aunque el sitio es estático, se implementaron medidas de seguridad razonables para proteger la infraestructura y los accesos. En un siguiente nivel, podría añadirse un WAF (Web Application Firewall) y políticas de seguridad más estrictas.

---

## 7. Proyección de Costos

### 7.1 Estimación de costos en ambiente de desarrollo

Para el ambiente de desarrollo se utilizó un **App Service Plan Free Tier** que no genera costo mensual. Además, los recursos de red (VNet y NSG) no tienen un costo significativo en entornos pequeños y de prueba.

**Estimación de costos de desarrollo:**
- App Service Plan Free Tier: $0/mes
- App Service: $0/mes
- Virtual Network: $0/mes (uso básico)
- Network Security Group: $0/mes (uso básico)

**Total estimado en desarrollo:** **$0/mes**

### 7.2 Proyección de costos en ambiente de producción

Para un ambiente de producción con al menos **1000 usuarios concurrentes**, se requiere un plan de App Service con mayor capacidad.

#### Supuestos de cálculo
- El sitio es estático y de bajo consumo de CPU.
- Se estiman 1000 usuarios concurrentes en picos de demanda.
- Se considera escalado horizontal para garantizar disponibilidad.
- Se asume un ancho de banda moderado por usuario.

#### Configuración recomendada
- **Plan de App Service**: Standard S2 o Premium P1v3.
- **Instancias**: 2 a 3 instancias para manejar la carga concurrente.
- **Evaluación de tráfico**: Si cada usuario consume un promedio de 300 KB por página, 1000 usuarios simultáneos generan hasta 300 MB por minuto en picos.
- **Ancho de banda mensual estimado**: 500 GB a 1 TB, dependiendo del uso.

#### Estimación de costos mensuales
| Concepto | Cantidad | Costo estimado mensual |
|----------|----------|-------------------------|
| App Service Plan Standard S2 | 3 instancias | ~$450 USD |
| Almacenamiento de App Service | incluido | ~$0 USD |
| Transferencia de datos | 1 TB | ~$80 USD |
| Supervisión básica | incluido | ~$0 USD |
| **Total aproximado** | | **$530 USD/mes** |

> Nota: Los costos pueden variar según la región de Azure y los niveles de tráfico real. Para un escenario inicial, 2 instancias Standard S2 podrían ser suficientes, reduciendo el costo a aproximadamente $300 USD/mes.

#### Alternativa más económica
Si se usa un plan **Standard S1** y se monitorea el comportamiento, la solución podría operar con un costo cercano a **$220 USD/mes** para 2 instancias, si el tráfico es moderado.

### 7.3 Observaciones de costos

- El **ambiente de desarrollo** puede mantenerse sin costo usando Free Tier.
- El **ambiente de producción** requiere un plan pagado y posiblemente balanceo por instancias.
- El mayor costo en producción suele ser el plan de App Service y la transferencia de datos.
- Los costos deben revisarse periódicamente con métricas reales de uso.

---

## 8. Ventajas del Modelo PaaS frente a Infraestructura Tradicional

### 8.1 Reducción de la complejidad operativa

Con PaaS, el proveedor administra la infraestructura subyacente, lo que reduce la carga de mantenimiento del equipo de TI. No es necesario configurar servidores físicos, sistemas operativos ni parches de seguridad.

### 8.2 Escalabilidad automática

Azure App Service permite escalar automáticamente según la demanda. Esto significa que la aplicación puede adaptar sus recursos sin necesidad de aprovisionamiento manual de hardware.

### 8.3 Despliegue más rápido

El ciclo de despliegue es más corto en PaaS, ya que los entornos se provisionan rápidamente y las aplicaciones se pueden subir directamente desde repositorios o paquetes.

### 8.4 Costos gestionados

Con PaaS se pagan únicamente los recursos consumidos y no se invierte en infraestructura física. En escenarios de desarrollo y prueba la opción Free Tier reduce costos significativamente.

### 8.5 Mantenimiento reducido

El proveedor gestiona actualizaciones, parches y disponibilidad de hardware. Esto libera al equipo para concentrarse en el desarrollo de la aplicación y no en la administración de servidores.

### 8.6 Seguridad integrada

PaaS ofrece características de seguridad integradas como certificados SSL, restricciones de red y monitoreo. Esto facilita cumplir con buenas prácticas sin una gran inversión en herramientas adicionales.

---

## 9. Conclusiones

El proyecto de TechNova Solutions demuestra que es viable implementar un sitio web corporativo profesional utilizando servicios cloud de bajo costo y con enfoque PaaS. Azure App Service permite reducir la complejidad operativa y concentrarse en el diseño y la experiencia del usuario.

La solución implementada cumple con los requisitos establecidos: diseño atractivo, contenido institucional, servicios claros, sección de contacto y seguridad básica. La arquitectura de Azure garantiza una base escalable y segura que puede evolucionar hacia un entorno de producción con mayor carga.

Se recomienda continuar con la evolución de la solución hacia capacidades dinámicas, integración de backend y monitoreo avanzado cuando la empresa necesite atender usuarios simultáneos de manera consistente.

---

## 10. Lecciones Aprendidas

### 10.1 Importancia de la documentación

Contar con documentación clara y estructurada facilita la implementación y la revisión del proyecto. Los informes, guías y checklist ayudan a mantener consistencia y reducen errores.

### 10.2 Valor de PaaS para proyectos pequeños

El modelo PaaS es ideal para proyectos con presupuesto limitado y necesidades de despliegue rápido, ya que elimina gran parte de la carga administrativa.

### 10.3 No subestimar la seguridad

Incluso un sitio estático necesita medidas básicas de seguridad como HTTPS, NSG y cabeceras de seguridad. Estos elementos cuentan para la profesionalización del proyecto.

### 10.4 Planificación de costos

Es clave distinguir entre el costo cero de desarrollo y el costo real de producción. Proyectar la demanda permite elegir un plan de servicio apropiado y evitar sobrecostos.

### 10.5 Escalabilidad desde el diseño

Diseñar para la nube implica pensar en escalabilidad desde el inicio. La elección de App Service facilita escalar sin rediseñar la aplicación.

---

## 11. Recomendaciones Finales

- Para producción con altas concurrencias, utilizar un plan de App Service de nivel Standard o Premium.
- Monitorear el consumo y ajustar la cantidad de instancias según el tráfico.
- Evaluar el uso de una CDN para mejorar la entrega de contenido estático.
- Incorporar almacenamiento en base de datos y un backend si el formulario requiere procesamiento real.
- Continuar documentando cambios y manteniendo un control de costos.

---

## 12. Anexos

### 12.1 Resumen de Recursos Azure
- Resource Group: `rg-technova`
- Virtual Network: `vnet-technova`
- Subnet: `subnet-app`
- Network Security Group: `nsg-technova`
- App Service Plan: `asp-technova`
- Web App: `technova`

### 12.2 URL de ejemplo

- Sitio web: `https://technova.azurewebsites.net`

### 12.3 Costo estimado para producción
- App Service Plan Standard S2 (3 instancias): aproximado **$450 USD/mes**
- Transferencia de datos (1 TB): aproximado **$80 USD/mes**
- Total estimado: **$530 USD/mes**

---

## 13. Formato para Word

Este informe está estructurado en formato de texto que puede copiarse directamente a un documento Word. Cada sección está numerada y organizada para facilitar su presentación.
