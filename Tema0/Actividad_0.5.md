---

### `Tema0/Actividad_0.5.md`

```markdown
# Actividad 0.5 - Práctica Servidor Web en Python

## Servidor Web Embebido (Ejemplo 1)
```bash
python3 -m http.server 8000

from http.server import HTTPServer, SimpleHTTPRequestHandler

def run_server(port=8000):
    server_address = ('', port)
    httpd = HTTPServer(server_address, SimpleHTTPRequestHandler)
    print(f"[*] Servidor Web iniciado en [http://0.0.0.0](http://0.0.0.0):{port}")
    try:
        httpd.serve_forever()
    except KeyboardInterrupt:
        httpd.server_close()

if __name__ == '__main__':
    run_server(8000)
python3 dummy_server.py
