# 04 - Modelo de amenazas: Por qué FIDO2 es resistente al phishing y ataques modernos

Este capítulo explica de forma profunda **por qué FIDO2 es considerado el estándar más seguro del mundo** para autenticación.

## 1. ¿Qué es un modelo de amenazas?

Un **modelo de amenazas** es un análisis estructurado que identifica:

- Qué ataques son posibles.
- Qué atacantes participan.
- Qué vectores utilizan.
- Qué controles los bloquean.

FIDO2 (Fast Identity Online v2) fue diseñado desde cero con un modelo de amenazas moderno, orientado a eliminar:

- Phishing.
- Robo de contraseñas.
- Replay attacks (ataques de repetición).
- MitM (Man in the Middle — hombre en el medio).
- Compromiso de base de datos.
- Ataques de ingeniería social avanzada.

## 2. ¿Qué amenaza FIDO2 quiere eliminar?

### 1. Phishing

El phishing es el ataque más exitoso del mundo. FIDO2 lo mitiga porque:

- La clave privada **nunca viaja**.
- La firma solo se genera si el dominio coincide exactamente.
- No hay contraseña que robar.

### 2. Replay attacks (ataques de repetición)

Los desafíos criptográficos **siempre son únicos**, por lo tanto:

- Un atacante no puede reutilizar firmas capturadas.

### 3. Robo de base de datos

FIDO2 usa **claves públicas individuales por sitio**, o sea:

- Si un servidor es comprometido, no se puede usar la información robada para autenticar a nadie.

### 4. MitM (Man in the Middle)

Como cada firma está ligada al dominio mediante WebAuthn (Web Authentication):

- Un ataque MITM no puede modificar el dominio sin invalidar la autenticación.

### 5. Ingeniería social

Incluso si un atacante convence a una víctima de "autenticar":

- La firma solo servirá para el dominio legítimo.
- Phishing de Google: no funciona.
- Phishing idéntico pero en otro dominio: no funciona.

## 3. ¿Qué hace a FIDO2 tan resistente?

### 1. Criptografía asimétrica

Cada sitio recibe una **clave pública única**, y la clave privada **queda dentro del autenticador**.
Nunca se puede extraer.

### 2. Origin binding (vinculación al origen)

La firma solo es válida si:

- El dominio coincide.
- El protocolo (HTTPS - Hypertext Transfer Protocol Secure) coincide.
- El contexto es el esperado.

Esto destruye el phishing de forma nativa.

### 3. Challenges (desafíos) únicos

Cada autenticación genera un Challenge único. Esto evita:

- Reutilización de tráfico.
- Reenvío.
- Suplantación.

### 4. Atestación

Los autenticadores pueden demostrar su legitimidad: "Soy un dispositivo FIDO2 genuino".
Esto evita:

- Autenticadores clonados.
- Hardware malicioso.

### 5. Sin secretos compartidos

No hay:

- Contraseñas.
- Tokens estáticos.
- TOTP reutilizables.
- SMS.

No existe nada que el atacante pueda copiar.

## 4. ¿Qué ataques bloquea específicamente FIDO2?

### Bloquea completamente

- Phishing clásico.
- Phishing avanzado.
- Captura de tráfico HTTPS.
- Malware que roba contraseñas.
- Ataques de SIM swapping.
- Ataques contra TOTP.
- Ataques contra códigos SMS.
- Ataques de Credential Stuffing (uso de contraseñas filtradas).

### Dificulta enormemente

- Keylogging hardware.
- Malware con acceso de usuario.

### No protege contra

- Compromiso del endpoint.
- Ataques físicos sofisticados.
- Ingeniería social fuera del flujo técnico (llamadas, chantaje, coerción).

## 5. Ejemplos aplicados

**Red Team:** permite identificar:

- Sistemas débiles que aún dependen de contraseña.
- Sitios sin WebAuthn.
- Configuraciones incorrectas.
- Procedimientos que pueden ser violados.

**Blue Team:** se debería diseñar:

- Accesos corporativos sin contraseñas.
- Eliminación de credenciales reutilizables.
- Protección contra phishing.

**DevSecOps:** se debería integrar:

- FIDO2 para acceso a repositorios.
- Autenticación de pipelines.
- Git signed commits con hardware.

## 6. Conclusión

FIDO2 ofrece protección porque:

- No hay secretos compartidos.
- No hay contraseñas.
- Cada sitio tiene su propia clave.
- Los desafíos son únicos.
- Las firmas dependen del dominio.
- El autenticador nunca expone la clave privada.

Esto lo convierte en el estándar más seguro disponible.
