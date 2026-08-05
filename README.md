# Gu-a-y-documentaci-n-del-despliegue-configuraci-n-de-Active-Directory
Guía y documentación del despliegue, configuración de Active Directory Domain Services (AD DS), creación de Dominio, Unidades Organizativas (OUs), Usuarios y Objetivas de Directiva de Grupo (GPOs) en Windows Server.

# 🏢 Implementación y Configuración de Active Directory (AD DS) en Windows Server

Este repositorio contiene la documentación detallada y evidencia gráfica del despliegue de un controlador de dominio utilizando **Active Directory Domain Services (AD DS)** en **Windows Server**, abarcando desde la instalación del rol hasta la gestión de usuarios, Unidades Organizativas (OU) y Directivas de Grupo (GPO).

---

## 🎯 Objetivos del Proyecto
1. Desplegar el rol de **AD DS** y configurar un nuevo bosque/dominio.
2. Promover el servidor a **Controlador de Dominio (DC)** y configurar servicios **DNS**.
3. Diseñar la jerarquía del dominio mediante **Unidades Organizativas (OUs)**.
4. Gestionar la creación de usuarios, grupos de seguridad y asignación de permisos.
5. Aplicar y probar **Directivas de Grupo (GPOs)** para la administración centralizada de clientes.

---

## 🛠️ Requisitos y Entorno
- **Sistema Operativo Servidor:** Windows Server (2019 / 2022).
- **Sistema Operativo Cliente:** Windows 10 / 11 Enterprise o Pro (unido al dominio).
- **Entorno de Virtualización:** Oracle VirtualBox / VMware Workstation.
- **Red:** Configuración de IP Estática en el servidor y resolución de nombres vía DNS local.

---
Fases de Configuración

### 1. Configuración Previa de Red
- Asignación de dirección IP estática en el servidor.
- Configuración del DNS preferido apuntando a la propia IP del servidor (`127.0.0.1` o IP estática asignada).

### 2. Instalación de Roles y Promoción
1. Instalación del rol **Servicios de dominio de Active Directory (AD DS)** desde el *Administrador del Servidor*.
2. Promoción del servidor a Controlador de Dominio (*Agregar un nuevo bosque*).
3. Establecimiento del FQDN del dominio (Ej: `laboratorio.local`).

### 3. Estructuración de Unidades Organizativas (OU) y Usuarios
1. Apertura de la consola *Usuarios y equipos de Active Directory* (`dsa.msc`).
2. Creación de la estructura organizativa (OUs por departamentos: *TI*, *RRHH*, *Finanzas*).
3. Creación de usuarios y asignación a sus respectivos grupos de seguridad.

### 4. Creación y Aplicación de Directivas de Grupo (GPO)
1. Apertura de la consola *Administración de directivas de grupo* (`gpmc.msc`).
2. Creación y vinculación de Objetos de Directiva de Grupo (GPO).
3. Configuración de reglas (Ej: bloqueo de Panel de Control, mapeo automático de unidades de red, directivas de contraseñas).
4. Verificación de actualización en el cliente mediante:
   ```cmd
   gpupdate /force
