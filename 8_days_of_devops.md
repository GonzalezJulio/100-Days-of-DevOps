# 📘 Día 8 – Instalación de Ansible (Controller)

En este día se dio un **paso clave en el camino DevOps**: la instalación y validación de **Ansible** como herramienta de automatización y gestión de configuración, utilizando el **Jump Host** como *Ansible Controller*.

---

## 🎯 Objetivo del ejercicio

* Utilizar el **Jump Host** como Ansible Controller
* Instalar **Ansible versión 4.7.0**
* Usar **exclusivamente `pip3`** para la instalación
* Asegurar que **todos los usuarios del sistema** puedan ejecutar comandos de Ansible

---

## 🧠 Conceptos clave aprendidos

### 🔹 ¿Qué es Ansible?

* Herramienta de **automatización y configuration management**
* **Agentless**: no requiere agentes en los servidores remotos
* Se comunica mediante **SSH**

### 🔹 Ansible Controller

* Es el servidor donde **Ansible está instalado**
* Desde aquí se ejecutan playbooks y comandos
* En este caso: **Jump Host**

Los App Servers **NO necesitan Ansible instalado**, solo:

* SSH
* Python

---

## 🧩 Instalación de Ansible

### Requisito del ejercicio

* Prohibido usar `yum`, `dnf` o `apt`
* Instalación obligatoria con `pip3`

### Comando ejecutado

```bash
sudo pip3 install ansible==4.7.0
```

📌 Uso de `sudo`:

* Permite una instalación **a nivel sistema**
* Hace que Ansible esté disponible para **todos los usuarios**

---

## 🔍 Verificación de la instalación

```bash
ansible --version
```

Salida relevante:

```text
ansible [core 2.11.x]
executable location = /usr/local/bin/ansible
```

### ⚠️ Nota importante

* Ansible **4.7.0** utiliza internamente **ansible-core 2.11.x**
* Ver `core 2.11.x` es **correcto y esperado**

---

## 📁 Ubicación de archivos importantes

* Binario:

```text
/usr/local/bin/ansible
```

* Paquete Python:

```text
/usr/local/lib/python3.x/site-packages/ansible
```

Esto confirma que Ansible está instalado **globalmente**.

---

## ✅ Validación contra el enunciado

| Requisito                 | Estado |
| ------------------------- | ------ |
| Uso de pip3               | ✅      |
| Versión 4.7.0             | ✅      |
| Instalación global        | ✅      |
| Jump Host como controller | ✅      |

---

## 🚀 Aplicación real en DevOps

Esta configuración es la base para:

* Ansible Playbooks
* Inventories
* Automatización de tareas
* CI/CD (Jenkins + Ansible)
* Gestión de múltiples servidores

