# Actividad 0.2 - UDP and TCP: Comparison of Transport Protocols

1. **Diferencias entre UDP y TCP:**
   - **TCP:** Orientado a conexión, fiable, garantiza la entrega ordenada de paquetes mediante confirmaciones (ACKs)[cite: 1].
   - **UDP:** Sin conexión, no garantiza la entrega ni el orden, orientado a la velocidad y baja latencia[cite: 1].

2. **¿Qué aplicaciones usan TCP?**
   - HTTP/HTTPS, SMTP, POP, IMAP, SSH, FTP[cite: 1].

3. **¿Qué aplicaciones usan UDP?**
   - DNS (puerto 53), DHCP, TFTP, Streaming, VoIP[cite: 1].

4. **¿Qué capa almacena el puerto?**
   - Capa de Transporte (Capa 4)[cite: 1].

5. **¿Qué capa almacena la dirección IP?**
   - Capa de Red / Internet (Capa 3)[cite: 1].

6. **¿Qué es el Three-Way Handshake?**
   - Proceso de negociación TCP en 3 pasos: `SYN` $\rightarrow$ `SYN-ACK` $\rightarrow$ `ACK`[cite: 1].
