# Día 6 – SELinux: Instalación y Deshabilitado Permanente

## 🧩 Objetivo del laboratorio
Instalar SELinux en App Server 1 y deshabilitarlo de forma permanente para pruebas iniciales.
El sistema se reiniciará más tarde para aplicar los cambios.

## 🔍 Análisis del problema
- SELinux puede no estar instalado en el servidor.
- Se requiere deshabilitarlo **permanentemente**, no temporalmente.
- No se debe reiniciar el servidor ahora.
- El validador ignora el estado actual mostrado por comandos (`getenforce`).

## 🧠 Razonamiento aplicado
1. **Instalar paquetes SELinux:**
   Usar el gestor de paquetes del sistema (yum/dnf) para instalar `selinux-policy` y `selinux-policy-targeted`.

2. **Deshabilitar SELinux permanentemente:**
   Editar el archivo de configuración persistente:
   ```
   /etc/selinux/config
   ```
   Cambiar la línea:
   ```text
   SELINUX=enforcing
   ```
   Por:
   ```text
   SELINUX=disabled
   ```
   - Esto garantiza que SELinux esté deshabilitado **en el próximo reboot**.
   - No se debe comentar ni duplicar la línea.

## 🛠 Comandos utilizados

### 1. Instalar paquetes SELinux
```bash
sudo yum install -y selinux-policy selinux-policy-targeted
```

### 2. Editar configuración
```bash
sudo vi /etc/selinux/config
# Cambiar SELINUX=enforcing → SELINUX=disabled
```

### 3. Verificación previa al reboot (opcional)
```bash
cat /etc/selinux/config | grep SELINUX
# Debe mostrar SELINUX=disabled
```

## ✅ Aprendizajes clave
- Diferencia entre **estado temporal** y **estado permanente** de SELinux
- Archivo de configuración persistente: `/etc/selinux/config`
- SELinux modes: enforcing / permissive / disabled
- Gestión de paquetes según la distro (yum/dnf en RHEL/CentOS)
