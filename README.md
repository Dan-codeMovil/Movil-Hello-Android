## Taller 2 - Arquitectura MVVM

### Respuestas a Preguntas Conceptuales

#### 1. ¿Qué problema resuelve el ViewModel en Android?

Permite mantener los datos y la lógica independientes de la UI y sobrevivir a cambios del ciclo de vida.<img width="442" height="58" alt="image" src="https://github.com/user-attachments/assets/a9f2fa44-52d9-4f63-93da-af485e8c427d" />

#### 2. ¿Por qué LiveData es "lifecycle-aware" y qué beneficio trae?

-	Solo envía datos cuando la vista está activa (STARTED o RESUMED).
-	Beneficios:
  o	Evita crashes por actualizar vistas destruidas.
  o	No hay fugas de memoria.
  o	No es necesario manejar manualmente el ciclo de vida.

#### 3. Explica con tus propias palabras el flujo de datos en MVVM

-	El View (Fragment) solicita datos o acciones al ViewModel.
-	El ViewModel procesa la lógica y pide datos al Repository.
-	El Repository obtiene los datos (API, BD, etc.).
-	Los datos regresan al ViewModel.
-	El ViewModel expone los datos mediante LiveData.
-	El View observa esos datos y actualiza la UI automáticamente.

#### 4. ¿Qué ventaja tiene usar Fragments vs múltiples Activities?

Los Fragments permiten reutilizar y manejar mejor la UI dentro de una sola Activity.

o	Mejor rendimiento (menos Activities).
o	Navegación más fluida
o	Reutilización de componentes
o	Mejor manejo con Navigation Component.


#### 5. ¿Cómo ayuda el Repository Pattern a la arquitectura?

Lo ayuda ya que actúa como una capa intermedia entre el ViewModel y las fuentes de datos.

o	Centraliza el acceso a datos.
o	Hace el código más limpio y mantenible.
o	Facilita pruebas (testing).

