# 01 - ¿Qué es FIDO2 (Fast IDentity Online 2)?

Este documento profundiza en el estándar **FIDO2 (Fast IDentity Online 2)**, su arquitectura, sus componentes y su importancia para la autenticación moderna. Es una extensión directa de la introducción previa y establece la base conceptual para comprender el resto del módulo.

## Definición General

**FIDO2 (Fast IDentity Online 2)** es un conjunto de estándares diseñados para permitir autenticación fuerte sin contraseñas, utilizando criptografía de clave pública y dispositivos seguros como autenticadores.

Su objetivo principal es reemplazar definitivamente las contraseñas, eliminando riesgos como:

- Phishing
- Robo de credenciales
- Ataques MITM (Man-In-The-Middle)
- Password spraying
- Reutilización de contraseñas

FIDO2 logra esto mediante dos tecnologías clave: **WebAuthn (Web Authentication)** y **CTAP2 (Client To Authenticator Protocol 2)**.

## Componentes Principales de FIDO2

### **1. WebAuthn (Web Authentication)**

Es una API soportada por navegadores modernos (Chrome, Firefox, Edge, Safari) que permite que un sitio web solicite autenticación usando claves criptográficas en lugar de contraseñas.

WebAuthn define cómo:

- Se generan nuevas credenciales.
- Se validan firmas criptográficas.
- Se vinculan claves públicas a dominios específicos.

Características clave:

- Las claves están asociadas a un dominio concreto (protección antiphishing).
- Usa desafíos criptográficos en lugar de contraseñas.
- El servidor nunca recibe claves privadas.

### **2. CTAP2 (Client To Authenticator Protocol 2)**

Es el protocolo que permite que un **autenticador externo** (un hardware key o un smartphone) se comunique con el navegador o con el sistema operativo.

Los autenticadores pueden usar:

- USB (Universal Serial Bus)
- NFC (Near Field Communication)
- BLE (Bluetooth Low Energy)

Funciones esenciales:

- Gestionar claves privadas dentro del hardware.
- Firmar desafíos sin revelar material sensible.
- Validar biometría local (como huella o rostro).

## Arquitectura Interna: ¿Cómo funciona FIDO2?

A alto nivel, el proceso involucra:

### **1. Registro (Attestation)**

El usuario registra un autenticador en un servicio.

Proceso:

- El servicio genera un desafío (challenge).
- El autenticador genera un par de claves: pública y privada.
- La clave privada queda protegida dentro del autenticador.
- La clave pública se envía al servidor.

### **2. Autenticación (Assertion)**

Cuando el usuario inicia sesión:

- El servicio envía otro desafío.
- El autenticador firma este desafío con la clave privada.
- El servidor verifica la firma usando la clave pública.

No hay contraseñas, ni SMS (Short Message Service), ni códigos TOTP (Time-based One-Time Password). Solo criptografía.

## ¿Por qué FIDO2 es tan resistente al phishing?

Porque las credenciales están asociadas criptográficamente al **dominio legítimo**.

Si un atacante crea:

```
  https://githuh.com
```

El autenticador simplemente no responde, porque la clave está vinculada a:

```
  https://github.com
```

No depende de la atención del usuario. Es seguridad por diseño.

## Pasos de Seguridad Clave

FIDO2 aporta:

- **Proof of Possession**: Solo quien tenga físicamente la clave puede autenticarse.
- **Proof of Presence**: Requiere toque, huella o acción deliberada.
- **Crypto Challenge**: Nunca hay secretos compartidos.

Esto elimina vectores completos de ataque.

## Autenticadores FIDO2: Tipos

### **1. Claves de hardware**

- YubiKey
- SoloKey
- Feitian
- Nitrokey

### **2. Smartphones**

- Android (mediante TEE — Trusted Execution Environment)
- iPhone (Secure Enclave)

### **3. Credenciales sincronizadas**

- Passkeys

  - Google
  - Apple
  - Microsoft

## Casos de Uso

### **DevSecOps (Development, Security and Operations)**

- Proteger accesos a GitHub y firmar commits.
- Seguridad en pipelines CI/CD (Continuous Integration / Continuous Delivery).

### **Red Team**

- Evaluar organizaciones que aún dependen de MFA débil.
- Construir escenarios donde la única forma de bypass es comprometer el dispositivo físico.

### **Blue Team**

- Implementar autenticación resistente a phishing.
- Reforzar Zero Trust mediante identidad fuerte.

### **Arquitectura AICO (AI-Integrated Cybersecurity Operations)**

- Integrar FIDO2 como base para identidad fuerte en sistemas automatizados.
- Diseñar accesos críticos donde solo operadores autorizados pueden interactuar.

## Conclusión

FIDO2 no es solo un reemplazo de contraseñas: es una arquitectura completa de autenticación moderna, resistente, compatible con Zero Trust y fundamental para entornos corporativos seguros.
