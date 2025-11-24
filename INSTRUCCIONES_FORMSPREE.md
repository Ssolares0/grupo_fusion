# Configuración de Formspree para el Formulario de Contacto

## ¿Qué es Formspree?

Formspree es un servicio que permite procesar formularios HTML y enviar los datos directamente a tu correo electrónico sin necesidad de código de servidor.

## Pasos para Configurar

### 1. Crear una cuenta en Formspree

1. Ve a [https://formspree.io](https://formspree.io)
2. Haz clic en "Sign Up" (Registrarse)
3. Puedes registrarte con tu correo electrónico o usar GitHub/Google

### 2. Crear un nuevo formulario

1. Una vez dentro de tu cuenta, haz clic en "+ New Form" (Nuevo Formulario)
2. Dale un nombre al formulario, por ejemplo: "Contacto Grupo Fusión"
3. Formspree te generará un ID único, algo como: `https://formspree.io/f/xwkgabcd`

### 3. Configurar el formulario en tu sitio web

1. Abre el archivo `index.html`
2. Busca la línea que dice:
   ```html
   <form action="https://formspree.io/f/TU_FORMSPREE_ID" method="POST">
   ```
3. Reemplaza `TU_FORMSPREE_ID` con el ID que te dio Formspree
   
   **Ejemplo:**
   ```html
   <form action="https://formspree.io/f/xwkgabcd" method="POST">
   ```

### 4. Verificar tu correo electrónico

La primera vez que alguien envíe un mensaje a través del formulario:
1. Formspree te enviará un correo de confirmación
2. Debes hacer clic en el enlace de confirmación
3. A partir de ese momento, recibirás todos los mensajes del formulario en tu correo

## Plan Gratuito de Formspree

El plan gratuito de Formspree incluye:
- 50 envíos por mes
- 1 formulario
- Almacenamiento básico de envíos
- Notificaciones por correo electrónico

**Nota:** Para mayor capacidad, puedes actualizar a un plan de pago.

## Configuración Adicional (Opcional)

### Personalizar el correo de destino

En tu panel de Formspree, puedes:
- Cambiar el correo electrónico donde recibes las notificaciones
- Configurar múltiples correos de destino
- Personalizar el asunto del correo

### Agregar protección contra spam

Formspree incluye protección básica contra spam. Para mayor protección:
1. Ve a la configuración de tu formulario en Formspree
2. Activa "reCAPTCHA" (puede requerir un plan de pago)

### Personalizar el mensaje de confirmación

Puedes agregar una página de confirmación personalizada agregando este campo oculto en tu formulario:

```html
<input type="hidden" name="_next" value="https://tudominio.com/gracias.html">
```

### Personalizar el asunto del correo

Puedes especificar el asunto del correo que recibirás:

```html
<input type="hidden" name="_subject" value="Nuevo mensaje de contacto - Grupo Fusión">
```

## Ejemplo de Implementación Completa

```html
<form action="https://formspree.io/f/xwkgabcd" method="POST">
    <!-- Campo oculto para personalizar el asunto -->
    <input type="hidden" name="_subject" value="Nuevo mensaje de contacto - Grupo Fusión">
    
    <!-- Campos del formulario -->
    <input type="text" name="nombre" required>
    <input type="email" name="correo" required>
    <input type="tel" name="telefono" required>
    <textarea name="comentario" required></textarea>
    
    <button type="submit">Enviar Mensaje</button>
</form>
```

## Solución de Problemas

### No recibo los correos
- Verifica tu carpeta de spam
- Confirma que has verificado tu correo en Formspree
- Revisa que el ID del formulario sea correcto

### El formulario no se envía
- Asegúrate de tener conexión a internet
- Verifica que el atributo `method="POST"` esté presente
- Comprueba que los campos `name` estén configurados

## Contacto de Soporte

Si tienes problemas, puedes:
- Visitar la documentación: [https://help.formspree.io](https://help.formspree.io)
- Contactar al soporte de Formspree directamente desde tu panel
