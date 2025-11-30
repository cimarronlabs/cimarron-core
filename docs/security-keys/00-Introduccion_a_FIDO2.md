# 00 - Introducción a FIDO2 (Fast IDentity Online 2)

Este documento forma parte del módulo **security-keys** dentro del laboratorio central de **Cimarrón Labs**. Su finalidad es establecer los conceptos fundamentales necesarios para comprender, implementar y evaluar tecnologías modernas de autenticación basadas en **FIDO2 (Fast IDentity Online 2)**.

---

## Propósito del Documento

* Explicar de forma clara los conceptos esenciales de FIDO2.
* Dar contexto técnico y estratégico para arquitecturas modernas de autenticación.
* Establecer la base teórica que se expandirá en los siguientes capítulos.
* Alinear estos conocimientos con el enfoque de Cimarrón Labs: seguridad aplicada, Zero Trust, AICO y automatización.

---

## ¿Qué es FIDO2 (Fast IDentity Online 2)?

FIDO2 es un estándar de autenticación diseñado para eliminar por completo el uso de contraseñas, usando en su lugar criptografía de clave pública y dispositivos seguros como llaves físicas o smartphones.

FIDO2 está compuesto por dos estándares principales:

### **1. WebAuthn (Web Authentication)**

Es la API que permite que los navegadores y los sitios web implementen autenticación sin contraseña.

* Define cómo se crean y validan las credenciales.
* Asocia las claves a dominios específicos.
* Protege contra phishing y ataques de intermediario.

### **2. CTAP2 (Client To Authenticator Protocol 2)**

Es el protocolo que permite que un dispositivo externo como una YubiKey, SoloKey, Feitian o un smartphone Android actúe como autenticador.

* Administra claves privadas dentro de hardware seguro.
* Firma desafíos criptográficos sin exponer material sensible.
* Puede comunicarse por USB (Universal Serial Bus), NFC (Near Field Communication) o BLE (Bluetooth Low Energy).

WebAuthn y CTAP2 trabajan juntos para formar el ecosistema FIDO2.

---

## Otros conceptos importantes

### **U2F (Universal 2nd Factor)**

Antecesor de FIDO2. Solo servía como segundo factor, no permitía autenticación sin contraseña.

### **Passkeys (Claves Sincronizadas FIDO2)**

Son credenciales basadas en FIDO2 pero almacenadas y sincronizadas en la nube por sistemas como Google, Apple o Microsoft. Facilitan el uso en múltiples dispositivos.

### **TEE (Trusted Execution Environment)**

Entorno seguro dentro del hardware donde se guardan claves privadas en dispositivos móviles.

---

## ¿Por qué FIDO2 es importante para la seguridad moderna?

* Elimina contraseñas y todos los riesgos asociados.
* Resiste completamente ataques de phishing.
* Reduce superficie de ataque en entornos corporativos.
* Se integra perfectamente con arquitecturas Zero Trust.
* Es compatible con DevSecOps y CI/CD (Continuous Integration / Continuous Delivery).
* Es recomendado por estándares modernos de seguridad, incluyendo NIST (National Institute of Standards and Technology).

En Cimarrón Labs, este estándar es pilar central para:

* Fortalecer accesos a repositorios.
* Firmar commits.
* Proteger infraestructura crítica.
* Diseñar sistemas defensivos.
* Evaluar sistemas vulnerables como parte del Red Team.

---

## Conclusión

FIDO2 representa el camino moderno hacia autenticación segura y resistente al phishing. Entender estos conceptos es fundamental para el desarrollo de arquitecturas avanzadas, operaciones AICO, DevSecOps, Red Team y Blue Team.


