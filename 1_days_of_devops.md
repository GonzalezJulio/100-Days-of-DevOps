<<<<<<< HEAD
# Día 1: Configuración de usuario de Linux con shell no interactivo
=======
# Creación de usuario no interactivo en App Server 3
>>>>>>> 6c7e0294bacc6af3aff8fb53bc69d1611b9d8be6

## Objetivo

Crear un usuario llamado `anita` en **App Server 3** con un **shell no interactivo**, según los requisitos del equipo de administración del sistema para herramientas de backup.

---

## Pasos realizados

### 1. Verificación del servidor y del shell

Conectarse al **jumphost** (`thor@jumphost`) y listar los shells disponibles:

```bash
cat /etc/shells
```

Resultado:

```
/bin/sh
/bin/bash
/usr/bin/sh
/usr/bin/bash
```

Buscar shells no interactivos:

```bash
which nologin
which false
```

Resultado:

```
/usr/sbin/nologin
/usr/bin/false
```

---

### 2. Conexión a App Server 3

Desde el jumphost, usar SSH para conectarse al servidor correcto (`stapp03`) con el usuario correspondiente (`banner`):

```bash
ssh banner@stapp03.stratos.xfusioncorp.com
```

Confirmar que estamos en el servidor correcto:

```bash
hostname
```

Resultado esperado:

```
stapp03
```

---

### 3. Creación del usuario `anita` con shell no interactivo

- Usuario a crear: `anita`
- Shell no interactivo elegido: `/usr/sbin/nologin`

Comandos utilizados con permisos de root:

```bash
sudo adduser -s /usr/sbin/nologin anita
```

Explicación:

- `sudo` → permisos de administrador  
- `adduser` → comando para crear usuario  
- `-s /usr/sbin/nologin` → asigna shell no interactivo  
- `anita` → nombre del usuario  

---

### 4. Verificación

Confirmar que el usuario se creó correctamente:

```bash
getent passwd anita
```

Salida esperada:

```
anita:x:1001:1001::/home/anita:/usr/sbin/nologin
```

Esto indica que:

- El usuario `anita` existe  
- Tiene el shell `/usr/sbin/nologin`  
- No puede iniciar sesión interactiva  

---

## Conclusión

<<<<<<< HEAD
El usuario **anita** fue creado con éxito en **App Server 3**, cumpliendo los requisitos de la herramienta de backup y garantizando que no pueda iniciar sesión de manera interactiva.
=======
El usuario **anita** fue creado con éxito en **App Server 3**, cumpliendo los requisitos de la herramienta de backup y garantizando que no pueda iniciar sesión de manera interactiva.
>>>>>>> 6c7e0294bacc6af3aff8fb53bc69d1611b9d8be6
