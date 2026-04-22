# Taller 1 - Hello Android


## Información del Estudiante

- Nombre: Daniel Eduardo Jaimes Montañez

- Código: 1099738794

- Fecha: 5/03/2026


## Respuestas


### 1. Función del AndroidManifest.xml

es el archivo principal de configuración de una aplicación Android. Define información esencial que el sistema necesita para ejecutar la app. Entre sus funciones principales están:

· Declarar las actividades (Activities), servicios y receptores de la aplicación.

· Indicar los permisos que necesita la app (por ejemplo acceso a internet o cámara).

· Definir el nombre, ícono y configuración básica de la aplicación.

· Especificar la actividad principal que se ejecuta al iniciar la app.


### 2. Diferencia entre activity_main.xml y MainActivity.kt

La diferencia principal es que uno define la interfaz y el otro la lógica.

· activity_main.xml

o Es un archivo de diseño (layout).

o Define cómo se ve la pantalla: botones, textos, imágenes, etc.

o Usa XML para organizar los elementos visuales.

· MainActivity.kt

o Es un archivo de código en Kotlin.

o Controla la lógica y el comportamiento de la pantalla.

o Aquí se programan acciones como responder a clics de botones o manejar datos.

### 3. Gestión de recursos en Android

La gestión de recursos en Android consiste en organizar y acceder a elementos externos al código, como:

· Imágenes

· Colores

· Textos

· Diseños (layouts)

· Iconos

· Estilos

Estos recursos se guardan en la carpeta res/ del proyecto y se organizan en subcarpetas, esto permite:

· Reutilizar recursos fácilmente

· Adaptar la app a diferentes idiomas y pantallas

· Mantener el código más ordenado




### 4. Aplicaciones famosas que usan Kotlin

Muchas aplicaciones populares usan Kotlin para desarrollar sus apps Android. Algunas son:

· Pinterest

· Trello

· Evernote

· Netflix

· Uber


## Capturas de Pantalla


![Captura del emulador](docs/captura_emulador.png)



## Taller 2 - Arquitectura MVVM

### Respuestas a Preguntas Conceptuales
#### 1. ¿Qué problema resuelve el ViewModel en Android?
El ViewModel resuelve el problema de la pérdida de datos cuando ocurren cambios de configuración (como rotar la pantalla). Permite almacenar y gestionar los datos de la UI de forma que sobrevivan a estos cambios, evitando tener que recargar información o perder el estado.

---

#### 2. ¿Por qué LiveData es "lifecycle-aware" y qué beneficio trae?
LiveData es "lifecycle-aware" porque reconoce el estado del ciclo de vida de componentes como Activities o Fragments. Esto significa que solo actualiza la UI cuando el componente está activo, evitando errores como fugas de memoria o crashes por intentar actualizar vistas que ya no existen.

---

#### 3. Explica con tus propias palabras el flujo de datos en MVVM
En MVVM, la vista (Fragment o Activity) observa al ViewModel. El ViewModel obtiene los datos desde el Repository, y este a su vez puede obtenerlos de una base de datos o de internet. Cuando los datos cambian, el ViewModel los actualiza y la vista se actualiza automáticamente sin necesidad de lógica adicional.

---

#### 4. ¿Qué ventaja tiene usar Fragments vs múltiples Activities?
Los Fragments permiten reutilizar componentes de UI y hacer interfaces más dinámicas dentro de una sola Activity. Esto mejora el rendimiento, facilita la navegación y hace que la aplicación sea más modular y mantenible.

---

#### 5. ¿Cómo ayuda el Repository Pattern a la arquitectura?
El Repository actúa como una capa intermedia entre el ViewModel y las fuentes de datos. Su ventaja es que centraliza el acceso a los datos, facilita el mantenimiento del código y permite cambiar la fuente de datos (por ejemplo, de API a base de datos) sin afectar otras partes de la aplicación.

---

### Diagrama de Arquitectura

    View (Fragment / Activity)
              ↓
         ViewModel
              ↓
         Repository
         ↓        ↓
    API / DB    Model
![img.png](img.png)