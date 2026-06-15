# 💻 Comandos Útiles - TechNova Solutions

Aquí encontrarás comandos útiles para diferentes tareas del proyecto.

---

## 🌐 Git - Desplegar en Azure

### Si Quieres Usar Git para Desplegar

#### 1. Inicializar Repositorio
```bash
cd c:\Users\Alumno USAID\Documents\PROYECTO EN NUBE\technova-web
git init
git config user.name "Tu Nombre"
git config user.email "tu-email@example.com"
```

#### 2. Agregar Archivos
```bash
git add .
git commit -m "Initial commit - TechNova website"
```

#### 3. Agregar Remote de Azure
En Azure Portal → Web App → Deployment Center → Local Git
Copiar la URL y reemplazar en:
```bash
git remote add azure <URL-DE-TU-AZURE>
```

#### 4. Desplegar (Push)
```bash
git push azure main
```

---

## ☁️ Azure CLI - Comandos

### Si Instalas Azure CLI

#### Instalar Azure CLI
```bash
# En Windows, descargar e instalar desde:
# https://learn.microsoft.com/cli/azure/install-azure-cli
```

#### Login en Azure
```bash
az login
```

#### Ver Suscripción
```bash
az account list --output table
```

#### Crear Resource Group
```bash
az group create \
  --name rg-technova \
  --location "East US"
```

#### Crear Virtual Network
```bash
az network vnet create \
  --resource-group rg-technova \
  --name vnet-technova \
  --address-prefix 10.0.0.0/16 \
  --subnet-name subnet-app \
  --subnet-prefix 10.0.1.0/24
```

#### Crear Network Security Group
```bash
az network nsg create \
  --resource-group rg-technova \
  --name nsg-technova
```

#### Crear App Service Plan
```bash
az appservice plan create \
  --name asp-technova \
  --resource-group rg-technova \
  --sku FREE
```

#### Crear Web App
```bash
az webapp create \
  --resource-group rg-technova \
  --plan asp-technova \
  --name technova \
  --runtime "STATIC:1.0"
```

#### Integrar VNet
```bash
az webapp vnet-integration add \
  --resource-group rg-technova \
  --name technova \
  --vnet vnet-technova \
  --subnet subnet-app
```

#### Ver URL de tu Web App
```bash
az webapp show \
  --resource-group rg-technova \
  --name technova \
  --query "defaultHostName" \
  --output tsv
```

---

## 📦 ZIP Deployment

### Si Quieres Desplegar un ZIP

#### 1. Crear ZIP de los Archivos
```bash
# En Windows (usando PowerShell)
Compress-Archive -Path "C:\ruta\technova-web\*" -DestinationPath "technova.zip"
```

#### 2. Desplegar el ZIP
```bash
az webapp deployment source config-zip \
  --resource-group rg-technova \
  --name technova \
  --src "C:\ruta\technova.zip"
```

---

## 🔍 Diagnósticos y Logs

### Ver Logs en Azure
```bash
# Tail logs (ver en tiempo real)
az webapp log tail \
  --resource-group rg-technova \
  --name technova
```

### Ver Estado de Despliegue
```bash
az webapp deployment operation list \
  --resource-group rg-technova \
  --name technova \
  --output table
```

### Reiniciar Web App
```bash
az webapp restart \
  --resource-group rg-technova \
  --name technova
```

---

## 📝 PowerShell - Tareas Windows

### Comprimir Carpeta (ZIP)
```powershell
# Navegar a la carpeta
cd "C:\Users\Alumno USAID\Documents\PROYECTO EN NUBE\technova-web"

# Crear ZIP
Compress-Archive -Path "." -DestinationPath "..\technova-web.zip" -Force
```

### Listar Archivos
```powershell
Get-ChildItem -Recurse -Force
```

### Verificar Estructura
```powershell
tree /F
```

---

## 🔗 URLs de Acceso

### URLs de Referencia
```
Azure Portal:        https://portal.azure.com
Documentación:       https://docs.microsoft.com/azure/
Azure CLI Docs:      https://learn.microsoft.com/cli/azure/
Kudu (tu sitio):     https://technova.scm.azurewebsites.net
Tu Sitio (después):  https://technova.azurewebsites.net
```

---

## 🧹 Limpieza (Eliminar Recursos)

### Eliminar Todo (si necesitas comenzar nuevamente)
```bash
# ⚠️ ADVERTENCIA: Esto eliminará todos los recursos
az group delete --name rg-technova --yes
```

### Eliminar Solo Web App
```bash
az webapp delete \
  --resource-group rg-technova \
  --name technova
```

---

## 📊 Monitoreo

### Ver Métricas (CPU, Memoria)
```bash
az monitor metrics list \
  --resource /subscriptions/{subscription-id}/resourceGroups/rg-technova/providers/Microsoft.Web/sites/technova \
  --metric "CpuTime" \
  --start-time "2024-01-01T00:00:00Z"
```

### Ver Alertas
```bash
az monitor metrics alert list \
  --resource-group rg-technova
```

---

## 🆘 Solución de Problemas (CLI)

### Verificar Conexión a Azure
```bash
az account show
```

### Ver Configuración de Web App
```bash
az webapp config show \
  --resource-group rg-technova \
  --name technova
```

### Ver Tamaño de Archivo
```bash
# En PowerShell
Get-ChildItem -Recurse | Measure-Object -Sum Length
```

---

## 📱 Pruebas Locales

### Con Python (si lo tienes instalado)
```bash
cd C:\Users\Alumno USAID\Documents\PROYECTO EN NUBE\technova-web
python -m http.server 8000
# Abre http://localhost:8000 en navegador
```

### Con Node.js (si lo tienes instalado)
```bash
# Instalar http-server
npm install -g http-server

# Ejecutar
cd C:\Users\Alumno USAID\Documents\PROYECTO EN NUBE\technova-web
http-server
# Abre http://localhost:8080
```

---

## ✨ Alias Útiles (Opcional)

Si usas PowerShell, puedes crear alias:

```powershell
# Agregar a tu perfil de PowerShell
Set-Alias -Name goto-project -Value "cd 'C:\Users\Alumno USAID\Documents\PROYECTO EN NUBE'"
Set-Alias -Name goto-web -Value "cd 'C:\Users\Alumno USAID\Documents\PROYECTO EN NUBE\technova-web'"
```

---

## 📋 Checklist de Comandos

### Para Implementación Rápida (Azure CLI)
```bash
[ ] az login
[ ] az group create (Resource Group)
[ ] az network vnet create (VNet)
[ ] az network nsg create (NSG)
[ ] az appservice plan create (Plan)
[ ] az webapp create (Web App)
[ ] az webapp vnet-integration add (VNet Integration)
[ ] az webapp deployment source config-zip (Deploy)
```

---

## 🎓 Recursos Útiles

### Documentación de Referencia
- Azure CLI Reference: https://docs.microsoft.com/cli/azure/
- PowerShell: https://docs.microsoft.com/powershell/
- Git: https://git-scm.com/doc

### Tutorials
- Azure for Students: https://azure.microsoft.com/free/students/
- Azure CLI Quickstart: https://docs.microsoft.com/cli/azure/get-started-with-azure-cli

---

## 💡 Tips Pro

### Guardar Credenciales (NO RECOMENDADO)
```bash
# ⚠️ Solo para desarrollo local, NUNCA en producción
az config set defaults.group=rg-technova
az config set defaults.web=technova
```

### Usando Variables de Entorno
```bash
$rg = "rg-technova"
$site = "technova"

# Usar en comandos
az webapp show --resource-group $rg --name $site
```

### Output en JSON
```bash
# Para procesar en scripts
az webapp list --output json > apps.json
```

---

## 🔐 Seguridad

### Nunca Guardes
```
❌ Passwords
❌ API Keys
❌ Connection Strings
❌ Credenciales en archivos
```

### Mejor Usa
```
✅ Azure Key Vault
✅ Environment Variables
✅ Azure Managed Identity
✅ Azure CLI (autenticación segura)
```

---

## 📞 Soporte

Si necesitas ayuda con los comandos:
- Documentación Azure: https://docs.microsoft.com
- Stack Overflow: https://stackoverflow.com/questions/tagged/azure
- Microsoft Learn: https://learn.microsoft.com/

---

**¡Estos comandos te ayudarán a implementar TechNova Solutions profesionalmente! 🚀**

Última actualización: Junio 2024
