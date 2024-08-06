## Configuración Inicial

1. Inicia un nuevo proyecto de Node.js y navega a la carpeta del proyecto.
2. Instala las dependencias necesarias: Express y jsonwebtoken.

## Endpoints de Autenticación

- **POST /login**
  - **Descripción:** Verifica credenciales y devuelve un token JWT.
  - **Cuerpo:**
    ```json
    {
      "username": "user",
      "password": "password"
    }
    ```
  - **Respuesta:** `{ "token": "<jwt_token>" }`

- **GET /verify**
  - **Descripción:** Verifica si el token JWT es válido y no ha expirado.
  - **Encabezado de Autorización:** `Bearer <jwt_token>`
  - **Respuesta:** `{ "message": "Token válido" }` si el token es válido.

  ## Consideraciones de Seguridad

- **Clave Secreta:** Asegúrate de mantener la clave secreta (`SECRET_KEY`) segura y no exponerla en el código fuente. Utiliza variables de entorno para almacenarla.
- **Expiración de Tokens:** Los tokens expiran después del tiempo especificado para minimizar el riesgo de uso indebido. Implementa la renovación de tokens si es necesario.
