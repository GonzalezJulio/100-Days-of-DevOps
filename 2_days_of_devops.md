# Día 2: Configuración temporal del usuario con vencimiento  

📅 Fecha: 28-01-2026

---

## 📌 Objetivo

Crear un usuario temporal llamado `rose` en **App Server 3** del **Stratos Datacenter**, configurando una **fecha de expiración** para limitar su acceso según las políticas del proyecto Nautilus.

---

## 🛠️ Pasos realizados

### 1️⃣ Conexión al servidor correcto

Desde el jumphost, se accedió a **App Server 3** utilizando SSH:

```bash
ssh banner@stapp03.stratos.xfusioncorp.com
```

Se verificó el hostname para confirmar el servidor:

```bash
hostname
```

Resultado esperado:

```
stapp03
```

---

### 2️⃣ Creación del usuario con fecha de vencimiento

Se creó el usuario `rose` (en minúsculas) configurando la fecha de expiración requerida:

```bash
sudo useradd -e 2027-01-28 rose
```

📌 Detalles del comando:
- `useradd` → crea el usuario
- `-e 2027-01-28` → define la fecha de expiración de la cuenta
- `rose` → nombre del usuario temporal

---

### 3️⃣ Verificación

Se validó la fecha de vencimiento del usuario con el siguiente comando:

```bash
sudo chage -l rose
```

Salida esperada (parcial):

```
Account expires : Jan 28, 2027
```

---

## ✅ Conclusión

El usuario **rose** fue creado exitosamente en **App Server 3** con una fecha de vencimiento configurada para el **28 de enero de 2027**, garantizando un acceso temporal controlado y cumpliendo con las buenas prácticas de administración de usuarios en Linux.