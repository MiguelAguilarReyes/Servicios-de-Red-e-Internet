# Actividad 0.3 - Práctica Telnet / HTTP

## Ejecución de peticiones manuales con Telnet

1. **Establecer conexión TCP:**
```bash
telnet [www.profesordeinformatica.com](https://www.profesordeinformatica.com) 80
GET /servicios/http/ HTTP/1.1
Host: [www.profesordeinformatica.com](https://www.profesordeinformatica.com)
HTTP/1.1 200 OK
Date: Wed, 23 Sep 2026 18:00:00 GMT
Server: Apache
Content-Type: text/html; charset=UTF-8

<html>...</html>
Enable-WindowsOptionalFeature -Online -FeatureName TelnetClient
