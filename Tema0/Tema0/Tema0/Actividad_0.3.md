# Actividad 0.3 - Práctica Telnet / HTTP

## 1. Introducción y Objetivos
El objetivo de esta práctica es analizar la mecánica del protocolo **HTTP/1.1** a bajo nivel mediante la herramienta de terminal **Telnet**. HTTP es un protocolo sin estado (*stateless*) basado en texto plano que opera en la capa de aplicación sobre el protocolo de transporte TCP (puerto por defecto 80).

Al utilizar Telnet, emulamos manualmente el comportamiento de un navegador web o agente de usuario (*User-Agent*), realizando la negociación TCP y la construcción artesanal de los encabezados de la petición HTTP Request.

---

## 2. Guía de Ejecución Paso a Paso

### Paso 1: Establecer la conexión TCP
Ejecuta el siguiente comando en la terminal para iniciar un *Three-Way Handshake* TCP contra el servidor remoto en el puerto 80:

```bash
telnet [www.profesordeinformatica.com](https://www.profesordeinformatica.com) 80
