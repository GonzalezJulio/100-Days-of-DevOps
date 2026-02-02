# Día 4 – Permisos de Archivos y Scripts en Linux

## Objetivo
Gestionar permisos de archivos para permitir la ejecución segura de scripts.

## Conceptos Clave
- **Permisos Linux:** lectura (r), escritura (w), ejecución (x).
- **Clases de usuarios:** owner (u), group (g), others (o), all (a).
- **Scripts Bash:** requieren permisos de lectura y ejecución.

## Comando Principal
- `chmod`: Cambia permisos de archivos.

## Modos Simbólicos
- `a+x`: agrega ejecución a todos.
- `a+rx`: agrega lectura y ejecución a todos.

## Caso Práctico
- Script: `/tmp/xfusioncorp.sh`
- Requisito: que **todos los usuarios** puedan ejecutarlo.

## Flujo Correcto
1. Ver permisos actuales.
2. Agregar permisos necesarios sin quitar otros.
3. Verificar permisos finales.

## Verificación
- `ls -l /ruta/al/script`
- Confirmar presencia de `r-x` para owner, group y others.

## Lecciones Aprendidas
- Solo `x` no alcanza para scripts de texto.
- `r+x` es obligatorio para ejecución correcta.
- Cambios mínimos = mayor seguridad.

---