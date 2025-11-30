# 02 - CTAP2 (Client to Authenticator Protocol 2) y WebAuthn (Web Authentication)

Este documento explica **cómo se comunican realmente** los autenticadores físicos con los navegadores y sistemas, punto medular para usar FIDO2 (Fast Identity Online v2) de manera profesional.

## 1. ¿Qué es CTAP2 (Client to Authenticator Protocol 2)?

**CTAP2 (Client to Authenticator Protocol 2)** es el protocolo que permite que un autenticador como una llave de seguridad USB (Universal Serial Bus), NFC (Near Field Communication) o BLE (Bluetooth Low Energy) se comunique con un cliente, es decir:

- Un navegador web
- Un sistema operativo
- Un servicio compatible con WebAuthn (Web Authentication)

En otras palabras, **CTAP2 es el puente de comunicación entre la llave física y el dispositivo donde nos queremos autenticar**.

### ¿Qué hace técnicamente CTAP2?

- Coordina la creación de claves públicas y privadas.
- Gestiona el registro de credenciales en los sitios.
- Autoriza la autenticación con desafíos criptográficos.
- Asegura la transmisión entre cliente y autenticador.

CTAP2 reemplaza y mejora **CTAP1 (Client to Authenticator Protocol 1)**, que era usado exclusivamente para U2F (Universal 2nd Factor). Con CTAP2 se habilita toda la potencia de FIDO2.

## 2. ¿Qué es WebAuthn (Web Authentication)?

**WebAuthn (Web Authentication)** es un estándar abierto creado por W3C (World Wide Web Consortium) que permite que aplicaciones web utilicen autenticación fuerte basada en criptografía.

Mientras CTAP2 es el protocolo "físico", WebAuthn es la capa del lado del navegador y la aplicación.

### WebAuthn define:

- Cómo un sitio web solicita registrar una clave.
- Cómo se solicita autenticar al usuario.
- El formato del challenge (desafío criptográfico).
- Cómo verificar la firma generada por el autenticador.

### Flujo básico de WebAuthn

1. El sitio envía un challenge al navegador.
2. El navegador lo pasa al autenticador mediante CTAP2.
3. El autenticador firma el challenge con la clave privada.
4. El navegador envía la firma al servidor.
5. El servidor verifica la firma usando la clave pública almacenada.

## 3. ¿Cómo interactúan CTAP2 y WebAuthn?

La relación es clara:

- **WebAuthn** vive en el navegador.
- **CTAP2** vive entre el navegador y el autenticador.

### El flujo completo sería asi:

```
    Servidor Web <-WebAuthn-> Navegador <-CTAP2-> Llave FIDO2
```

Ambos juntos son los que permiten:

- Autenticación sin contraseñas (passwordless)
- Factores de hardware seguros
- Uso de biometría como parte de la autenticación

Esto convierte a FIDO2 en uno de los sistemas más resistentes contra phishing y ataques de ingeniería social.
