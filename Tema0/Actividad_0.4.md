### `Tema0/Actividad_0.4.md`

```markdown
# Actividad 0.4 - Usando cURL

## 5 Ejemplos de uso del comando cURL

1. **Obtener el contenido HTML de una página:**
```bash
curl [https://www.google.com](https://www.google.com)
curl -o pagina_debian.html [https://www.debian.org](https://www.debian.org)
curl -I [https://www.debian.org](https://www.debian.org)
curl -X POST -d "usuario=asir&clave=1234" [https://ejemplo.com/login](https://ejemplo.com/login)
curl -L [http://google.com](http://google.com)
