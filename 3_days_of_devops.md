# Día 3 – Gestión de SSH y Seguridad Básica

## Objetivo
Fortalecer la seguridad de los servidores Linux restringiendo accesos inseguros mediante SSH.

## Conceptos Clave
- **SSH (Secure Shell):** Protocolo para acceso remoto seguro.
- **sshd:** Servicio/daemon del lado servidor.
- **Acceso root:** Riesgoso si se permite por SSH directamente.
- **Principio de mínimo privilegio:** Acceder con usuarios normales y elevar privilegios solo cuando sea necesario.

## Archivos Importantes
- `/etc/ssh/sshd_config`: Configuración del servidor SSH.

## Parámetros Relevantes
- `PermitRootLogin no`: Deshabilita el login directo del usuario root.
- Comentarios (`#`): Líneas comentadas no se aplican.

## Flujo de Trabajo Seguro
1. Conectarse por SSH con un usuario normal.
2. Editar configuración del servidor SSH.
3. Aplicar cambios y reiniciar el servicio.
4. Verificar que root no pueda loguearse por SSH.

## Comandos Conceptuales
- Editar configuración: usar un editor disponible (vi).
- Reiniciar servicio: `systemctl restart sshd`
- Verificación: intentar login como root (debe fallar).

## Buenas Prácticas
- Usar autenticación por clave pública/privada.
- Evitar accesos directos como root.
- Aplicar cambios en todos los servidores requeridos.

---