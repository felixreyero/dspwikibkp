Para subir un widget personalizado a SAP Analytics Cloud (SAC), sigue estos pasos:

1. Preparar el Widget
Asegúrate de que tu widget esté completo el mismo debe contener los siguientes archivos: 
Widget.json/Main.js/style.js
 
Empaqueta el widget en un archivo .zip. Esto debería incluir todos los archivos necesarios, como widget.json, main.js, style.js, y cualquier otro recurso que tu widget utilice.
El ZIP debe contener los tres recursos del widget y se conservará en una misma carpeta junto con el json para poder subir ambos a SAC. 

2. Acceder a SAP Analytics Cloud
Inicia sesión en tu instancia de SAP Analytics Cloud con una cuenta que tenga permisos de administrador o desarrollador.

3. Ir a la Sección de Custom Widgets
Desde la pantalla principal de SAC, ve a la Configuración.
Navega hasta la opción Custom Widgets (Widgets Personalizados) en el menú de configuración.

4. Subir el Widget
En la pantalla de Custom Widgets, haz clic en el botón + (Agregar).
Aparecerá un cuadro de diálogo donde puedes cargar tu archivo .zip. Selecciona el archivo comprimido de tu widget y haz clic en Subir.
Asegúrate de proporcionar un nombre y descripción claros para el widget si te lo solicita.
  
5. Verificar el Widget
Una vez subido, el widget debería aparecer en la lista de Widgets Personalizados.
Puedes verificar que todo esté en orden seleccionándolo de la lista.

6. Usar el Widget en un Dashboard o Story
Crea o abre un dashboard o story en SAC.
Selecciona Insertar y busca tu widget en la sección de Widgets Personalizados.
Arrastra y suelta el widget en el canvas, y configúralo según tus necesidades.

7. Permisos Insuficientes o Licencia Limitada
Si no encuentras la opción para subir un widget personalizado en SAP Analytics Cloud (SAC), es posible que sea debido a uno de los siguientes motivos:

•Permisos Insuficientes
Asegúrate de que tu cuenta tenga los permisos adecuados para crear y gestionar widgets personalizados. Necesitarás permisos de administrador o desarrollador.

•Licencia o Versión
No todas las versiones de SAP Analytics Cloud permiten la creación o importación de widgets personalizados. Verifica si tu instancia de SAC soporta widgets personalizados. En algunos casos, esta funcionalidad puede estar restringida o no habilitada en versiones específicas.

[Gauche_Widget.zip](uploads/25ebf0a445bf2ffc4dde4aebadcc135a/Gauche_Widget.zip)

[style.js](uploads/5b46bb51233fabcf38bd01f7cbe39bde/style.js)

[main.js](uploads/fca6ede9862c4c3ffba26295e923efe2/main.js)

[widget.json](uploads/4c9766942eaf6c416499cb6080cd6ba3/widget.json)