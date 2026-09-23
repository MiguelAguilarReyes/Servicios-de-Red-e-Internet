# Actividad 0.1 - HTTP Introduction

## Cuestiones
1. **¿Quién, dónde y cuándo se crea el primer servidor web?**
   - **Creador:** Tim Berners-Lee.
   - **Lugar:** CERN (Organización Europea para la Investigación Nuclear)[cite: 1].
   - **Año:** 1990[cite: 1].

2. **¿Qué es la pila de protocolos usados por HTTP?**
   - Es el modelo **TCP/IP** (HTTP en Aplicación, TCP en Transporte, IP en Red)[cite: 1].

3. **Componentes de una URL:**
   - Esquema/Protocolo (`http://`), Dominio (`ejemplo.com`), Puerto (`:80`), Ruta (`/dir/`) y Recurso (`index.html`)[cite: 1].

4. **Pasos en la recuperación de una página web mediante HTTP:**
   - Resolución DNS $\rightarrow$ Handshake TCP (puerto 80) $\rightarrow$ Petición HTTP Request $\rightarrow$ Respuesta HTTP Response $\rightarrow$ Cierre o Keep-Alive[cite: 1].

5. **Diferencia entre páginas estáticas y dinámicas:**
   - **Estáticas:** El servidor entrega el archivo HTML/recurso directamente sin procesar.
   - **Dinámicas:** El servidor ejecuta código (Python, PHP, Node.js) en tiempo real para generar la página.
