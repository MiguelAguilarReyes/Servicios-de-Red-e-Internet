# Actividad 0.5 - Práctica Servidor Web en Python

## 1. Introducción y Arquitectura
Python incluye en su biblioteca estándar módulos integrados (`http.server`) que permiten levantar servidores web HTTP funcionales en cuestión de segundos sin necesidad de instalar o configurar suites como Apache o Nginx. Son ideales para entornos de desarrollo local, pruebas de conectividad en laboratorio o compartición rápida de archivos.

---

## 2. Métodos de Despliegue Ejecutados

### Ejemplo 1: Servidor HTTP Embebido mediante línea de comandos
Levanta un servidor de archivos estáticos que sirve el directorio actual en el puerto asignado:

```bash
python3 -m http.server 8000
