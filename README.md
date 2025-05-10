# 🧠 Guía Completa de Comandos Linux: De Junior a Senior

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/a/af/Tux.png" width="200" />
</p>

---

## 🐣 Nivel Junior

### 📂 1. Gestión de Directorios y Archivos

**Navegación:**

```bash
pwd                 # Mostrar directorio actual
cd /ruta            # Ir a una ruta absoluta
cd ..               # Subir un nivel
cd ~                # Ir al home del usuario
ls -lh              # Listar archivos con tamaño legible
```

**Manipulación:**

```bash
cp archivo destino      # Copiar archivos
mv archivo nuevo_nombre # Mover o renombrar archivos
rm archivo              # Eliminar archivo
mkdir carpeta           # Crear carpeta
rmdir carpeta           # Eliminar carpeta vacía
```

---

### 📝 2. Visualización y edición básica

```bash
cat archivo.txt     # Mostrar contenido
more archivo.txt    # Navegación por página
nano archivo.txt    # Editor simple
```

---

### 🔍 3. Búsqueda básica

```bash
grep "texto" archivo.txt     # Buscar texto
find . -name "*.txt"         # Buscar archivos por patrón
```

---

### ⚙️ 4. Permisos básicos

```bash
chmod +x script.sh            # Dar permisos de ejecución
chmod 755 archivo.sh          # Permisos específicos
chown usuario:grupo archivo   # Cambiar propietario
```

---

### 📦 5. Compresión básica

```bash
tar -cvf archivo.tar carpeta  # Crear archivo .tar
tar -xvf archivo.tar          # Extraer archivo .tar
zip archivo.zip archivo       # Comprimir a .zip
unzip archivo.zip             # Descomprimir .zip
```

---

### 🌐 6. Red y descargas

```bash
ping google.com               # Verificar conectividad
wget URL                      # Descargar desde web
curl -O URL                   # Descargar con curl
```

---

## 🧱 Nivel Intermedio (Mid-Level)

### 🧩 7. Gestión avanzada de archivos

```bash
rsync -av carpeta/ destino/   # Sincronizar archivos
stat archivo                  # Ver detalles de archivo
file archivo                  # Identificar tipo de archivo
basename /ruta/archivo        # Obtener solo el nombre de archivo
dirname /ruta/archivo         # Obtener solo el directorio del archivo
```

---

### ⌛ 8. Procesos y monitoreo

```bash
ps aux                        # Ver procesos
kill -9 PID                   # Terminar proceso
htop                          # Monitor interactivo (mejor que top)
jobs                          # Ver trabajos en segundo plano
bg, fg                        # Enviar trabajos al fondo o traer al frente
nice -n 10 comando            # Ejecutar con prioridad
```

---

### 🧠 9. Variables de entorno y configuración

```bash
echo $PATH                    # Mostrar variable PATH
export VAR=valor              # Definir variable temporal
nano ~/.bashrc                # Archivo de configuración personal
alias gs='git status'         # Crear alias
unalias gs                    # Eliminar alias
env                          # Ver todas las variables
```

---

### 📊 10. Espacio en disco

```bash
df -h                         # Espacio libre por partición
du -sh carpeta/              # Tamaño de carpeta específica
ncdu                         # Análisis visual del uso de disco
ls -lhS                      # Archivos ordenados por tamaño
```

---

### 👥 11. Gestión de usuarios y grupos

```bash
sudo adduser nombre_usuario            # Crear nuevo usuario
sudo userdel -r nombre_usuario         # Eliminar usuario y su home
sudo groupadd nombre_grupo            # Crear grupo
sudo usermod -aG nombre_grupo usuario # Agregar usuario a grupo
id nombre_usuario                     # Ver grupos de un usuario
```

Cambiar contraseña o shell:

```bash
passwd nombre_usuario                 # Cambiar contraseña
chsh -s /bin/bash nombre_usuario      # Cambiar shell por defecto
```

Ver todos los usuarios y grupos:

```bash
cut -d: -f1 /etc/passwd               # Listar usuarios
cut -d: -f1 /etc/group                # Listar grupos
```

---

### 🧪 12. Control de versiones y diferencia de archivos

```bash
diff archivo1 archivo2        # Comparar archivos
cmp archivo1 archivo2         # Comparar binarios
comm archivo1 archivo2        # Líneas comunes y distintas
```

---

### 🔄 13. Redireccionamiento y pipes

```bash
comando > archivo.txt         # Redirigir salida (sobrescribe)
comando >> archivo.txt        # Redirigir salida (agrega)
comando < archivo.txt         # Entrada desde archivo
comando1 | comando2           # Pipe: salida -> entrada
tee archivo.txt               # Guardar salida y mostrar en pantalla
```

---

### 📒 14. journalctl y logs del sistema

```bash
journalctl                         # Mostrar todos los logs
journalctl -xe                     # Mostrar errores recientes y detallados
journalctl -u nginx                # Logs de un servicio específico
journalctl -f                      # Logs en tiempo real (como tail -f)
journalctl --since "1 hour ago"   # Logs desde hace 1 hora
journalctl -p err                 # Solo errores
journalctl -k                     # Solo logs del kernel
```

**Niveles de prioridad:**

* 0 emerg   (el sistema no sirve)
* 1 alert   (acción inmediata requerida)
* 2 crit    (error crítico)
* 3 err     (errores)
* 4 warning (advertencias)
* 5 notice  (avisos normales)
* 6 info    (información)
* 7 debug   (depuración)

---

## 🧙‍♂️ Nivel Senior

### 🧠 15. Expresiones regulares con grep, sed y awk

```bash
grep -E 'error|fail' log.txt          # Buscar múltiples patrones
sed 's/error/ERROR/g' archivo.txt     # Reemplazar texto
awk '{print $1, $3}' archivo.txt      # Extraer columnas
```

---

### 🧵 16. Bash scripting

```bash
#!/bin/bash
# Script básico
echo "Hola, $USER"

for archivo in *.txt; do
    echo "Procesando $archivo"
done
```

Variables, condicionales y funciones:

```bash
if [ -f archivo ]; then
    echo "Existe"
fi

mi_funcion() {
    echo "Hola $1"
}
```

---

### 🔐 17. Seguridad y auditoría

```bash
ufw enable / ufw status         # Firewall básico
iptables -L                     # Reglas de firewall
last / who / w                  # Sesiones y usuarios conectados
```

---

### 📋 18. Logs y monitoreo del sistema

```bash
tail -f /var/log/syslog         # Ver logs en tiempo real
journalctl -xe                 # Eventos recientes con systemd
```

---

### 🗂️ 19. Montaje de discos

```bash
mount /dev/sdb1 /mnt/disco      # Montar disco manualmente
umount /mnt/disco               # Desmontar
lsblk                           # Ver dispositivos de bloque
```

---

### 🔄 20. Cron y tareas programadas

```bash
crontab -e
# * * * * * comando
# m h dom mon dow
```

Ejemplo: ejecutar cada día a las 2 AM:

```bash
0 2 * * * /ruta/script.sh
```

---

### 🧩 21. Paquetes y servicios (Debian/Ubuntu)

```bash
apt update && apt upgrade       # Actualizar sistema
apt install nombre_paquete      # Instalar
systemctl start nginx           # Iniciar servicio
systemctl enable nginx          # Habilitar al arranque
```

---

### 🐳 22. Introducción a contenedores y Docker

```bash
docker ps                        # Contenedores activos
docker images                    # Ver imágenes
docker run -it ubuntu bash       # Iniciar contenedor interactivo
```

---

### ⚡ 23. SSH y administración remota

```bash
ssh usuario@host                 # Conexión SSH
scp archivo.txt usuario@host:/destino  # Copiar archivo vía SSH
```

---

### 🧠 24. Trucos y productividad

```bash
!!                   # Repite el último comando
!n                   # Repite el comando número n
Ctrl + r             # Búsqueda inversa de comandos
Ctrl + l             # Limpia terminal (como clear)
```

---

## 📚 Recursos Recomendados

* [https://explainshell.com](https://explainshell.com)
* [https://linuxjourney.com](https://linuxjourney.com)
* [https://tldr.sh](https://tldr.sh)

¿Quieres que agregue secciones para Kubernetes, scripting avanzado o automatización con Ansible?
