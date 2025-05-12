# ELEVATION 2 - Privilegios Ocultos en Windows

En este laboratorio deberás explorar un servidor Windows corporativo, identificar credenciales expuestas, descubrir la contraseña de un usuario clave mediante fuerza bruta y aprovechar una mala configuración para escalar privilegios hasta convertirte en administrador.

En este laboratorio aprenderás:

- Enumeración de usuarios y contraseñas en entornos Windows
- Uso de `Hydra` y `rockyou.txt` para ataques de fuerza bruta
- Acceso remoto vía SSH, SMB o WinRM
- Escalada de privilegios en Windows a través de configuración de grupo
- Lectura de flags como usuario administrador


<how-to-start>
   
## 🌱 Cómo iniciar este laboratorio

Sigue las siguientes instrucciones para comenzar:

1. **Descarga la máquina virtual** desde este [enlace](https://storage.googleapis.com/cybersecurity-machines/elevation-windows-machine.ova).
2. **Importa la máquina** en tu gestor de virtualización preferido (VirtualBox, VMware, etc.).
3. Una vez iniciada la máquina, ¡ya puedes comenzar con el laboratorio!
</how-to-start>


## 📄 Instrucciones

Estás frente a un servidor Windows con múltiples usuarios. Tu objetivo es obtener privilegios de administrador accediendo como el único usuario con una configuración peligrosa.

1. **Descubre la dirección IP de la máquina ELEVATION 2.**: Usa herramientas como `nmap`, `netdiscover` o `arp-scan`.

2. **Accede al recurso compartido de archivos (SMB).**: Busca archivos que contengan usuarios y contraseñas visibles.

3. **Realiza un ataque de fuerza bruta con Hydra.**

4. **Accede al sistema con el usuario que tiene privilegios ocultos.**

5. **Verifica si puedes escalar a Administrador.**

6. **Busca la flag final.**


**Recuerda:** a veces no necesitas vulnerabilidades técnicas, solo una mala práctica de seguridad.

¡Feliz hackeo!
