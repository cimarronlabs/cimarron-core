# Claves de Seguridad FIDO2 / WebAuthn

Este módulo forma parte del laboratorio central de **Cimarrón Labs**, enfocado en la investigación aplicada, la arquitectura defensiva y la integración de tecnologías modernas de autenticación sin contraseña.

Su objetivo es documentar de manera clara y profesional todo el proceso de adopción, configuración y análisis de seguridad relacionado con **FIDO2/WebAuthn**, incluyendo casos de uso para entornos DevSecOps, Red Team, Blue Team y AICO.

## Objetivos del Módulo

- Implementar autenticación resistente al phishing en servicios críticos.
- Comprender y documentar el funcionamiento interno de FIDO2/WebAuthn.
- Evaluar amenazas y limitaciones en entornos reales.
- Integrar claves físicas o biométricas en GitHub, Proton, Google y sistemas propios.
- Desarrollar guías aplicables a organizaciones y proyectos.

## ¿Qué es FIDO2/WebAuthn?

FIDO2 es un estándar de autenticación moderna basado en criptografía de clave pública. Permite que un usuario se autentique mediante una clave privada almacenada en un dispositivo seguro (como una YubiKey o un smartphone) sin necesidad de contraseñas.

- **WebAuthn**: Protocolo que permite que navegadores y servicios web usen claves de seguridad.
- **CTAP2**: Protocolo que permite que dispositivos externos actúen como llaves físicas.

Esta combinación elimina contraseñas, reduce superficie de ataque y protege contra phishing, robo de credenciales, MITM y ataques de re‑utilización.

## Uso de un Smartphone como Clave FIDO2

Los dispositivos Android modernos permiten actuar como llaves FIDO2 vía:

- Huella digital
- Secure Enclave / Trusted Execution Environment
- USB, NFC o Bluetooth

Esto permite comenzar sin hardware dedicado. (Más económico)

El procedimiento general consiste en:

1. Acceder a un servicio que soporte FIDO2.
2. Elegir “Clave de Seguridad”.
3. Seleccionar “Dispositivo Android”.
4. Confirmar con biometría.

## Servicios Implementados

Este repositorio documenta la configuración real en servicios utilizados por Cimarrón Labs:

- GitHub (cimarron-core)
- Proton (correo seguro)
- Google (cuentas de respaldo)

## Casos de Uso

### **DevSecOps / AICO**

- Acceso al repositorio protegido por clave.
- Signing de commits.
- Integración passwordless en aplicaciones propias.

### **Blue Team**

- Eliminación de vectores de phishing.
- Autenticación resistente a MITM.
- Capacidades para Zero Trust.

### **Red Team**

- Evaluación de entornos con MFA débil.
- Demostración de bypass imposibles sin comprometer el dispositivo físico.
- Modelos de ataque alternativos.

## Estructura del Directorio

```
docs/security-keys/
    00-Introduccion_a_FIDO2.md
    01-Que_es_FIDO2.md
    02-CATP2_y_WebAuthn.md
```

## Licencia

Este módulo se publica bajo la licencia del repositorio principal de **cimarron-core**.
