# Proyecto InnovaSys – Automatización con Ansible

## 📌 Descripción
Este proyecto implementa un servidor multi-servicio para la empresa ficticia **InnovaSys** utilizando **Ansible**.  
El servidor se configura automáticamente con:
- Un portal web interno con **Apache2**.
- Un recurso compartido centralizado con **Samba**.

El objetivo es demostrar el uso de **roles de Ansible**, **variables**, **handlers** e **idempotencia** para un despliegue limpio y profesional.

---

## 🖥️ Entorno de Laboratorio
- **Nodo de Control:** Linux Lite (`192.168.10.151`) – ansible-control
- **Nodo Gestionado:** Ubuntu Server 24.04 (`192.168.10.100`) – servidor-innovasys

---

## ⚙️ Requisitos Previos
1. Tener conectividad SSH desde el nodo de control hacia el nodo gestionado.
2. Ansible instalado en el nodo de control.
3. Configurar el inventario `inventory.ini` con la IP del servidor gestionado.

Ejemplo de `inventory.ini`:

```ini
[innovasys]
192.168.10.100 ansible_user=usuario ansible_ssh_private_key_file=~/.ssh/id_rsa
```

▶️ **Ejecución del Playbook**  
Para configurar el servidor ejecutar:

```bash
ansible-playbook -i inventory.ini site.yml
```

✅ **Verificación**  
- Abrir un navegador en Linux Lite e ir a:  
```text
http://192.168.10.100
```
Debería mostrar:  
```text
Bienvenidos a la Intranet de InnovaSys
```

- Abrir el gestor de archivos en Linux Lite y conectarse a:  
```text
smb://192.168.10.100/Proyectos
```
Acceder con usuario: `devuser1`  
Contraseña: `Innova.2025`  
Crear un archivo de prueba dentro del recurso compartido.

📂 **Estructura del Proyecto**
```bash
innovaSys-ansible/
├── ansible.cfg
├── inventory.ini
├── site.yml
├── roles/
│   ├── apache/
│   │   ├── tasks/main.yml
│   │   ├── handlers/main.yml
│   │   ├── templates/index.html.j2
│   │   └── vars/main.yml
│   └── samba/
│       ├── tasks/main.yml
│       ├── handlers/main.yml
│       ├── templates/smb.conf.j2
│       └── vars/main.yml
```

✍️ **Autor**  
Cristhian Angeo B. Romero Vega  
Proyecto académico – Universidad (2025)
