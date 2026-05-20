# Documentación del Servidor FTP en Debian

# Instalación de vsftpd
Contenido que debes poner en docs/proyecto.md:
markdown
# Documentación del Servidor FTP en Debian

## Instalación de vsftpd

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install vsftpd -y
Configuración del firewall
bash
sudo nft add rule ip filter input tcp dport 21 ct state new accept
Configuración de vsftpd.conf
Archivo /etc/vsftpd.conf con las siguientes líneas:

text
listen=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
chroot_local_user=YES
allow_writeable_chroot=YES
seccomp_sandbox=NO
Creación de usuario FTP
bash
sudo useradd -m ftp_user
sudo passwd ftp_user
Conexión desde FileZilla
IP del servidor: 192.168.1.194

Puerto: 21

Usuario: ftp_user

Contraseña: (la que asignaste)

Operaciones realizadas
Conexión al servidor - Exitosa

Creación de carpeta pruebas_ftp - Captura adjunta

Subida de archivo FTP.pdf - Captura adjunta

Descarga de archivo - Captura adjunta

Plan de despliegue
Aspecto	Descripción
Tecnología	vsftpd
Sistema operativo	Debian 13 (Trixie)
Puerto	21/TCP
Firewall	nftables
