# Laboratorio ELEVATION 2

Este laboratorio está diseñado para que los alumnos comprendan cómo una mala política de contraseñas y la asignación inadecuada de privilegios pueden derivar en una escalada total de privilegios en un entorno Windows.

En este laboratorio los estudiantes aprenderán:

- A explorar recursos compartidos (SMB) para obtener información sensible
- A realizar ataques de fuerza bruta con Hydra y `rockyou.txt`
- A conectarse remotamente como usuarios estándar
- A identificar usuarios con privilegios de administrador ocultos
- A acceder a archivos sensibles como `Administrator`


## 🖥️ Especificaciones de la máquina

- **Sistema operativo:** Windows Server 2019 o 2022
- **Nombre de host:** `elevation2-lab`
- **Usuarios creados:**

| Usuario     | Contraseña          | Grupo              |
|-------------|---------------------|---------------------|
| parker      | `?AMERICA?`         | Users               |
| valentine   | `BreakingBad90`     | Users               |
| redfield    | `5Tr0ngPaSw0rd`     | Users               |
| kennedy     | `123kennedy456`     | Users               |
| wong        | `password123`       | Administrators ✅   |

- **Archivo sensible compartido por SMB:** `C:\users.txt`

- **Directorio compartido (SMB):** `C:\` compartido como `share` (solo lectura pública)

- **Flag final:** `C:\Users\Administrator\Desktop\flag.txt`



## Pasos esperados por el alumno

1. **Descubre la IP del servidor**
   - Utiliza `nmap`, `netdiscover` o similar

2. **Conecta vía SMB**
   - Accede al recurso compartido `\\IP\share` sin autenticación

3. **Obtiene `users.txt`**
   - Identifica credenciales completas salvo para `wong`
   - La pista textual indica que es una contraseña débil

4. **Realiza fuerza bruta con Hydra**
   - Apunta a SSH (si habilitado), WinRM (`5985`) o RDP (`3389`)
   - Usa:
     ```bash
     hydra -l wong -P /usr/share/wordlists/rockyou.txt ssh://<IP>
     ```

5. **Accede como `wong`** y comprueba que tiene permisos de administrador

6. **Lee la flag en el escritorio de Administrator**
   - Verifica si puede acceder directamente a:
     ```
     C:\Users\Administrator\Desktop\flag.txt
     ```