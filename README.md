\# Proyecto InnovaSys – Automatización con Ansible



\## 📌 Descripción

Este proyecto implementa un servidor multi-servicio para la empresa ficticia \*\*InnovaSys\*\* utilizando \*\*Ansible\*\*.  

El servidor se configura automáticamente con:

\- Un portal web interno con \*\*Apache2\*\*.

\- Un recurso compartido centralizado con \*\*Samba\*\*.



El objetivo es demostrar el uso de \*\*roles de Ansible\*\*, \*\*variables\*\*, \*\*handlers\*\* e \*\*idempotencia\*\* para un despliegue limpio y profesional.



---



\## 🖥️ Entorno de Laboratorio

\- \*\*Nodo de Control:\*\* Linux Lite (ansible-control)

\- \*\*Nodo Gestionado:\*\* Ubuntu Server 24.04 (servidor-innovasys)



---



\## ⚙️ Requisitos Previos

1\. Tener conectividad SSH desde el nodo de control hacia el nodo gestionado.

2\. Ansible instalado en el nodo de control.

3\. Configurar el inventario `inventory.ini` con la IP del servidor gestionado.



Ejemplo:

```ini

\[innovasys]

192.168.56.10 ansible\_user=usuario ansible\_ssh\_private\_key\_file=~/.ssh/id\_rsa



