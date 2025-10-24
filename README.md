# Login-ISTII
Asignación para la materia de ISTII del BTSJCH BUAP.

Este es un proyecto web simple que implementa un formulario de inicio de sesión seguro (basado en cliente) con un número limitado de intentos y una página de bienvenida protegida.
El enfoque principal del proyecto es la estética visual, replicando el efecto "Glassmorphism" (vidrio esmerilado) popular en las interfaces de usuario modernas.
Descripción
El proyecto consta de dos páginas:
 * login.html: La página de inicio de sesión.
   * Solicita un nombre de usuario y una contraseña.
   * Valida las credenciales contra una lista predefinida.
   * Permite un máximo de 3 intentos fallidos.
   * Al fallar 3 intentos, el formulario se bloquea.
   * Al tener éxito, redirige a home.html.
 * home.html: La página de bienvenida "protegida".
   * Muestra un mensaje de bienvenida.
   * Incluye un reproductor de vídeo de YouTube incrustado y responsivo.
   * Proporciona un botón para "Cerrar Sesión" (regresar a login.html).
Requerimientos
Para ejecutar este proyecto, solo necesitas un navegador web moderno que soporte:
 * HTML5
 * CSS3 (específicamente backdrop-filter)
 * JavaScript (ES6)
No hay dependencias de frameworks, librerías externas o compiladores.
Uso
 * Clona o descarga este repositorio.
 * ¡IMPORTANTE! Asegúrate de que los archivos login.html y home.html estén en la misma carpeta raíz para que la redirección funcione correctamente.
 * Abre el archivo login.html en tu navegador web.
 * Introduce una de las siguientes credenciales para iniciar sesión:
Credenciales de Acceso
| Usuario | Contraseña |
|---|---|
| BTSJCH | BUAP |
| GRUPO | admin2025 |
Diagrama UML - Flujo de Autenticación
Este diagrama de actividad muestra la lógica de validación de credenciales y el manejo de los 3 intentos fallidos antes del bloqueo.
graph TD
    A[INICIO] --> B{Usuario envía formulario};
    B --> C{Obtener y limpiar credenciales};
    C --> D{¿Credenciales correctas?};
    
    D -- Sí --> E[Mostrar éxito: Redirigiendo...];
    E --> F[Redirigir a home.html];
    F --> Z(FIN - Éxito);
    
    D -- No --> G[Restar 1 intento];
    G --> H{¿Intentos > 0?};
    
    H -- Sí --> I[Mostrar error. Intentos restantes];
    I --> B;
    
    H -- No --> J[Mostrar bloqueo y Deshabilitar formulario];
    J --> Z(FIN - Bloqueado);

