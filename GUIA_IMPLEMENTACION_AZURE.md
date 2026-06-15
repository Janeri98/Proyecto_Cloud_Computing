# 📘 Guía de Implementación - TechNova Solutions en Azure

## Requisitos Previos

1. **Cuenta de Azure**: Si eres estudiante, solicita **Azure for Students** (crédito gratuito)
2. **Instalación Local**: Git, Visual Studio Code (opcional)
3. **El sitio web** ya está creado en la carpeta `technova-web`

---

## 🔧 PASO 1: Configurar Suscripción y Recursos Azure

### 1.1 Crear/Usar Suscripción Azure
- Accede a [Azure Portal](https://portal.azure.com)
- Inicia sesión con tu cuenta educativa
- Verifica tener crédito disponible

### 1.2 Crear un Resource Group
1. En Azure Portal, ve a **Resource Groups**
2. Click en **+ Create**
3. Configurar:
   - **Name**: `rg-technova`
   - **Region**: `East US` (o cercana)
4. Click **Review + create** → **Create**

---

## 🌐 PASO 2: Configurar Red Virtual y Seguridad

### 2.1 Crear Virtual Network (VNet)
1. En Azure Portal, busca **Virtual Networks**
2. Click **+ Create**
3. Configurar:
   - **Resource Group**: `rg-technova`
   - **Name**: `vnet-technova`
   - **Region**: Igual al Resource Group
   - **IPv4 address space**: `10.0.0.0/16`
4. Click **Next: IP Addresses**

### 2.2 Crear Subred
1. En la sección de subredes, click **+ Add subnet**
2. Configurar:
   - **Subnet name**: `subnet-app`
   - **Subnet address range**: `10.0.1.0/24`
3. Click **Add**
4. Click **Review + create** → **Create**

### 2.3 Crear Network Security Group (NSG)
1. Busca **Network Security Groups**
2. Click **+ Create**
3. Configurar:
   - **Name**: `nsg-technova`
   - **Resource Group**: `rg-technova`
4. Click **Create**

### 2.4 Configurar Reglas de NSG
1. Abre el NSG creado
2. Ve a **Inbound security rules** → **+ Add**
3. Agregar regla para HTTP:
   - **Source**: Any
   - **Source port ranges**: *
   - **Destination**: Any
   - **Service**: HTTP (puerto 80)
   - **Action**: Allow
   - **Name**: `allow-http`
4. Click **Add**

5. Repetir para HTTPS:
   - **Service**: HTTPS (puerto 443)
   - **Name**: `allow-https`
6. Click **Add**

### 2.5 Asociar NSG a Subred
1. En el NSG, ve a **Subnets** → **+ Associate**
2. Seleccionar:
   - **Virtual network**: `vnet-technova`
   - **Subnet**: `subnet-app`
3. Click **OK**

---

## 🖥️ PASO 3: Crear App Service Plan y Web App

### 3.1 Crear App Service Plan
1. Busca **App Service Plans**
2. Click **+ Create**
3. Configurar:
   - **Resource Group**: `rg-technova`
   - **Name**: `asp-technova`
   - **Operating System**: Windows
   - **Region**: Igual a otros recursos
   - **Pricing Tier**: **Free Tier** (F1) - Sin costo
4. Click **Review + create** → **Create**

### 3.2 Crear Web App
1. Busca **App Services**
2. Click **+ Create** → **Web App**
3. Configurar:
   - **Resource Group**: `rg-technova`
   - **Name**: `technova` (o nombre único)
   - **Publish**: Code
   - **Runtime stack**: HTML (Static Content)
   - **Operating System**: Windows
   - **Region**: Igual a otros recursos
   - **App Service Plan**: `asp-technova` (Free tier)
4. Click **Review + create** → **Create**

**Tu URL será**: `https://technova.azurewebsites.net` (ajusta el nombre)

---

## 🔗 PASO 4: Integrar Web App con VNet

### 4.1 Habilitar VNet Integration
1. Abre tu Web App creada
2. Ve a **Settings** → **Networking**
3. Click **VNet integration** → **+ Add VNet**
4. Seleccionar:
   - **Virtual Network**: `vnet-technova`
   - **Subnet**: `subnet-app`
5. Click **OK**

### 4.2 Configurar Access Restrictions
1. En la misma sección de **Networking**
2. Ve a **Access Restrictions**
3. Opcionalmente, configurar restricciones de IP
4. Asegúrate que HTTP/HTTPS estén permitidos

---

## 📤 PASO 5: Desplegar el Sitio Web

### OPCIÓN A: Usar Azure Portal (Recomendado para principiantes)

#### A1. Preparar archivos
1. Comprime la carpeta `technova-web` completa:
   - Incluye: `index.html`, carpeta `css/`, carpeta `js/`

#### A2. Desplegar en Azure Portal
1. Abre tu Web App
2. Ve a **Deployment** → **Deployment Center**
3. Selecciona **Local Git** o **GitHub**
4. Si usas Local Git:
   - Copia el Git Clone URL
   - En tu PC, abre terminal en la carpeta del proyecto
   - Ejecuta:
   ```bash
   git init
   git add .
   git commit -m "Initial commit - TechNova website"
   git remote add azure <Git-Clone-URL>
   git push azure main
   ```

#### A3: Alternativa - Despliegue Manual ZIP
1. En tu Web App → **Development Tools** → **App Service Editor**
2. Sube los archivos manualmente
3. O usa **Kudu** (https://technova.scm.azurewebsites.net)

### OPCIÓN B: Usar Azure CLI (Avanzado)

```bash
# Instala Azure CLI desde https://learn.microsoft.com/cli/azure/install-azure-cli

# Login en Azure
az login

# Crear Web App
az webapp create --resource-group rg-technova --name technova --plan asp-technova

# Desplegar archivos
az webapp deployment source config-zip --resource-group rg-technova --name technova --src <ruta-zip>
```

---

## ✅ PASO 6: Verificar Despliegue

1. **Accede a tu sitio**:
   - URL: `https://technova.azurewebsites.net`
   - O el nombre que hayas elegido

2. **Verifica que funcionen**:
   - ✅ Todas las secciones carguen correctamente
   - ✅ Responsive en móvil
   - ✅ Menú de navegación funcione
   - ✅ Formulario de contacto responda

3. **Revisa logs** (si hay errores):
   - En la Web App → **Monitoring** → **Log stream**

---

## 📊 Monitoreo y Administración

### Ver Costos
- **Azure Portal** → **Cost Management** → Verificar gasto mensual
- Con Free Tier + Azure for Students: ~$0/mes

### Reiniciar Web App
1. Ve a tu Web App
2. Click **Restart** (arriba)

### Ver Actividad
1. **Activity log** en el Resource Group
2. **Metrics** en la Web App

---

## 🚀 Mejoras Opcionales

### Agregar Dominio Personalizado
1. En Web App → **Custom domains**
2. Agregar dominio propio (si tienes)

### Habilitar HTTPS Automático
1. Web App → **TLS/SSL settings**
2. Azure genera certificado automáticamente

### Configurar CI/CD
1. Conectar GitHub o Azure DevOps
2. Despliegues automáticos al hacer push

---

## 📝 Resumen de Recursos Creados

| Recurso | Nombre | Propósito |
|---------|--------|----------|
| Resource Group | `rg-technova` | Contenedor para todos los recursos |
| Virtual Network | `vnet-technova` | Red privada |
| Subnet | `subnet-app` | Subred para App Service |
| NSG | `nsg-technova` | Control de tráfico |
| App Service Plan | `asp-technova` | Plan de hospedaje (Free) |
| Web App | `technova` | Tu sitio web |

---

## 🆘 Solución de Problemas

### "Sitio no carga"
- Verifica que `index.html` esté en la raíz
- Revisa logs en **Log stream**

### "Archivo CSS/JS no carga"
- Asegúrate que `css/` y `js/` estén incluidas
- Revisa rutas relativas en HTML

### "Error 500"
- Reinicia Web App
- Verifica que sea hospedaje estático (no necesita runtime)

### "Costos muy altos"
- Asegúrate de usar **Free Tier** para App Service Plan
- Usa Azure for Students para crédito gratuito

---

## 📧 Contacto para Soporte

Para consultas técnicas:
- Email: info@technova.com
- Documentación Azure: https://docs.microsoft.com/azure/
- Soporte educativo: Tu institución educativa

---

**¡Tu sitio TechNova Solutions está listo para el mundo! 🌍**
