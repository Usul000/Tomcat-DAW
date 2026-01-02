# Tomcat-DAW


Práctica de Apache Tomcat para la asignatura Despliegue de Aplicaciones Web (2º DAW)

## 📚 Contenido de la práctica

### Parte 1: Tomcat en Windows con XAMPP
- ✅ Arranque y configuración inicial
- ✅ Acceso a opciones de gestión
- ✅ Ejemplos de funcionamiento
- ✅ Despliegue de aplicación WAR
- ✅ Cambio de puerto

### Parte 2: Tomcat en Linux (Lubuntu 25.04)
- ✅ Instalación y configuración
- ✅ Despliegue de aplicación web

### Parte 3: Securización SSL/HTTPS
- ✅ Certificados SSL
- ✅ Configuración HTTPS

### Parte 4: Integración con IDE
- ✅ Configuración IDE (Visual Studio Code / IntelliJ / Eclipse)

### Parte 5: Cuestiones teóricas
- ✅ Versiones de Tomcat según Java
- ✅ Otros servidores de aplicaciones
- ✅ Herramientas de pruebas de carga
- ✅ Monitorización

## 🛠️ Tecnologías utilizadas
- Apache Tomcat 11
- Java 21
- Windows 7 + XAMPP
- Lubuntu 25.04
- OpenSSL (para certificados)

## 👤 Autor: Iván Varela Cernadas - 2º DAW

## 📄 Licencia
Práctica educativa - CIFP Rodolfo Ucha (Ferrol)

Estructura:

Tomcat-DAW/
├── README.md
├── 01-Windows-XAMPP/
│   ├── capturas/
│   │   ├── 1.1-arranque-inicial.png
│   │   ├── 1.2-manager-app.png
│   │   ├── 1.3-ejemplos.png
│   │   ├── 1.4-despliegue-war.png
│   │   └── 1.5-cambio-puerto.png
│   ├── configs/
│   │   ├── server.xml
│   │   └── tomcat-users.xml
│   └── apps/
│       └── Sample.war
├── 02-Linux-Lubuntu/
│   ├── capturas/
│   │   ├── 2.1-instalacion.png
│   │   ├── 2.1-configuracion.png
│   │   └── 2.2-despliegue.png
│   ├── configs/
│   │   ├── server.xml
│   │   └── tomcat-users.xml
│   └── scripts/
│       └── install-tomcat.sh
├── 03-SSL-Securizacion/
│   ├── capturas/
│   │   ├── certificado-creado.png
│   │   └── https-funcionando.png
│   └── configs/
│       └── server.xml-con-ssl
├── 04-Integracion-IDE/
│   ├── capturas/
│   │   ├── ide-configurado.png
│   │   └── app-corriendo.png
│   └── proyecto-ejemplo/
├── 05-Cuestiones/
│   └── respuestas.md
└── PDF-Final/
    └── Tarea3_1_Iván_Varela_Cernadas

    ######## SOLUCIÓN DO EXERCIZO ########

1️⃣ WINDOWS + XAMPP
1.1 Arranque

Panel XAMPP → botón "Start" en Tomcat
Navegador: http://localhost:8080
Captura: Página inicio Tomcat

1.2 Gestión
Archivo: xampp/tomcat/conf/tomcat-users.xml
xml<role rolename="manager-gui"/>
<role rolename="admin-gui"/>
<user username="admin" password="admin" roles="manager-gui,admin-gui"/>

Reiniciar Tomcat
Captura: Manager App funcionando

1.3 Ejemplos

Clic en "Examples" → elegir uno (ej: Servlets)
Captura: Ejemplo ejecutándose

1.4 Desplegar WAR

Manager App → "WAR file to deploy" → seleccionar Sample.war → Deploy
Captura: Aplicación desplegada y accesible

1.5 Cambiar puerto
Archivo: xampp/tomcat/conf/server.xml
xml<Connector port="9090" protocol="HTTP/1.1" ... />

Reiniciar → acceder: http://localhost:9090
Captura: Tomcat en nuevo puerto


2️⃣ LINUX (LUBUNTU)
2.1 Instalación
bashsudo apt update
sudo apt install default-jdk
wget https://dlcdn.apache.org/tomcat/tomcat-11/[versión]/bin/apache-tomcat-11.x.tar.gz
sudo tar -xzvf apache-tomcat*.tar.gz -C /opt/
sudo ln -s /opt/apache-tomcat-11.x /opt/tomcat
Configurar usuario: Igual que Windows en tomcat-users.xml
bash/opt/tomcat/bin/startup.sh

Capturas: Instalación + Manager App

2.2 Desplegar WAR

Copiar Sample.war a /opt/tomcat/webapps/
O usar Manager App
Captura: App funcionando


3️⃣ SSL
bashkeytool -genkey -alias tomcat -keyalg RSA -keystore /ruta/keystore.jks
server.xml:
xml<Connector port="8443" protocol="HTTP/1.1" SSLEnabled="true"
    keystoreFile="/ruta/keystore.jks" keystorePass="tupassword"/>

Captura: https://localhost:8443


4️⃣ IDE (Visual Studio Code)

Instalar extensión: "Tomcat for Java"
Agregar servidor Tomcat
Deploy proyecto


Captura: App corriendo desde VSCode

La dificultad la definiría así:
Dificultad: ⭐⭐⭐ (3/5)

Parte Windows: FÁCIL
Parte Linux: MEDIA.
En concreto, la parte de 
SSL: MEDIA-ALTA y la del IdE con Visua Code ha sido fácil. 
