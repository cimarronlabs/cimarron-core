# 03 - Diferencias entre FIDO2 (Fast Identity Online v2), U2F (Universal 2nd Factor) y WebAuthn (Web Authentication)

Este capítulo aclara las diferencias entre los tres pilares del ecosistema moderno de autenticación fuerte.

## 1. U2F (Universal 2nd Factor)

U2F (Universal 2nd Factor) fue el estándar original creado por FIDO Alliance para brindar **un segundo factor de autenticación basado en hardware**.

### Características principales

* **Requiere contraseña + llave física**.
* No soporta autenticación sin contraseñas.
* Usa el protocolo **CTAP1 (Client to Authenticator Protocol 1)**.
* Funciona solo para "segundo factor" (2FA — Two Factor Authentication).
* Limitado en capacidades criptográficas comparado con FIDO2 (Fast Identity Online v2).

### ¿Qué problemas resolvía?

* Phishing.
* Claves TOTP (Time-based One-Time Password) robadas.
* SIM swapping (intercambio malicioso de tarjeta SIM — Subscriber Identity Module).

### Ejemplos aplicados

1. **Red Team:** saber que un sistema usa U2F (Universal 2nd Factor) dice que aún necesita contraseña, lo cual deja más superficie de ataque.
2. **Arquitectura defensiva:** migrar a FIDO2 (Fast Identity Online v2) para reducir la dependencia de contraseñas.

## 2. FIDO2 (Fast Identity Online v2)

FIDO2 (Fast Identity Online v2) es la evolución del estándar U2F (Universal 2nd Factor) y habilita **autenticación completa sin contraseñas**.

FIDO2 combina dos componentes:

* **WebAuthn (Web Authentication):** Lado navegador/servidor.
* **CTAP2 (Client to Authenticator Protocol 2):** Lado autenticador.

### Características principales

* Permite **passwordless (autenticación sin contraseñas)**.
* Puede ser primer factor, segundo factor o ambos.
* Soporta biometría.
* Más opciones criptográficas.
* Diseño moderno y escalable.

### Ejemplos aplicados

1. **DevSecOps (Development, Security and Operations):** integrar FIDO2 en accesos a pipelines elimina credenciales estáticas.
2. **Ciberinteligencia:** detectar uso de FIDO2 (Fast Identity Online v2) indica un nivel de madurez alto.

## 3. WebAuthn (Web Authentication)

WebAuthn no es un tipo de llave, es **el estándar que implementan los navegadores y servidores**.

Es la API que permite a un sitio web:

* Registrar un autenticador.
* Autenticar un usuario mediante desafíos.
* Validar firmas con claves públicas.

### WebAuthn gobierna:

* Qué campos recibe el servidor.
* Qué formatos se usan.
* Cómo se firma el challenge.
* Cómo se valida la autenticación.

### Ejemplos aplicados

1. **OSINT (Open Source Intelligence):** detectando soporte WebAuthn, se puede medir la exposición real de un sistema.
2. **Arquitectura de seguridad:** se integraría en las aplicaciones internas de una empresa para mejorar su postura.

## 4. Cómo se relacionan entre sí...

### Relación jerárquica

* **U2F (Universal 2nd Factor):**  versión antigua, segundo factor.
* **FIDO2 (Fast Identity Online v2):** estándar moderno que incluye WebAuthn y CTAP2.
* **WebAuthn (Web Authentication):** API y estándar para la web.
* **CTAP2 (Client to Authenticator Protocol 2):** protocolo entre navegador y autenticador.

### Comparación simple

| Tecnología | Rol                              | Protocolo        | Nivel de seguridad              |
| ---------- | -------------------------------- | ---------------- | ------------------------------- |
| U2F        | Segundo factor                   | CTAP1            | Alto, dependiente de contraseña |
| WebAuthn   | Estándar web                     | N/A              | Depende del autenticador        |
| CTAP2      | Comunicación con el autenticador | CTAP2            | Muy alto                        |
| FIDO2      | Framework completo               | WebAuthn + CTAP2 | Máximo nivel, Passwordless      |

## 5. Conclusión

* **U2F:** ya es viejo, solo 2FA.
* **WebAuthn:** es la especificación del navegador y servidor.
* **CTAP2:** es la especificación del autenticador.
* **FIDO2:** es el estándar moderno que los une.
