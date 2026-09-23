# Actividad 0.4 - Usando cURL

## 1. Concepto e Importancia
`curl` (*Client URL*) es una herramienta de línea de comandos utilizada para transferir datos con sintaxis de URL. Soporta múltiples protocolos de la capa de aplicación (HTTP, HTTPS, FTP, FTPS, SFTP, SMTP, etc.) y es fundamental en el trabajo diario de administración de sistemas e infraestructura de red para diagnosticar y depurar servicios de red.

---

## 2. Ejemplos Detallados de Uso Práctico

### Ejemplo 1: Descarga y visualización simple del cuerpo HTML
Realiza una petición `GET` básica y muestra el cuerpo de la respuesta por pantalla:
```bash
curl [https://www.google.com](https://www.google.com)
