# Inventory App - Android Basics with Compose

Aplicación de gestión de inventario desarrollada con **Jetpack Compose** y persistencia local mediante la biblioteca **Room**.

**Codelab:** [Read and update data with Room (Lectura y actualización de datos con Room)](https://developer.android.com/codelabs/basic-android-kotlin-compose-update-data-room?hl=es-419#0)  
**Autor:** Freddy Marcelo Bravo Ponce

---

## 📱 Descripción del Proyecto

Inventory App permite gestionar productos de un inventario en tiempo real. Implementa un flujo de datos reactivo y unidireccional que sincroniza la interfaz gráfica con la base de datos SQLite local a través de Room y Kotlin Coroutines (Flow / StateFlow).

---

## 🚀 Funcionalidades Implementadas

- **Lectura Reactiva con Flow**: Consultas al DAO que emiten cambios en tiempo real ante inserciones, actualizaciones o eliminaciones.
- **Patrón Repositorio**: Desacoplamiento entre la base de datos Room (`OfflineItemsRepository`) y los ViewModels.
- **Gestión de Estado con StateFlow**: Transformación de flujos fríos a flujos calientes con `stateIn` y manejo de ciclo de vida con `SharingStarted.WhileSubscribed(5000L)`.
- **Inserción de Artículos**: Validación de entrada y persistencia con `ItemEntryViewModel`.
- **Venta de Productos**: Decremento atómico del stock con `reduceQuantityByOne()` y deshabilitación automática del botón al agotarse el producto.
- **Edición de Artículos**: Precarga de información existente en `ItemEditViewModel` y persistencia con `updateItem()`.
- **Eliminación Segura**: Diálogo modal de confirmación (`DeleteConfirmationDialog`) previo al borrado definitivo con `deleteItem()`.
- **Inyección Manual de Dependencias**: Configuración centralizada de proveedores con `AppViewModelProvider`.

---

## 🛠️ Arquitectura y Tecnologías

- **Lenguaje**: Kotlin
- **UI Toolkit**: Jetpack Compose (Material 3)
- **Persistencia**: Room Database (SQLite)
- **Concurrencia**: Kotlin Coroutines & Flow (StateFlow)
- **Navegación**: Jetpack Navigation Compose con argumentos seguros (`SavedStateHandle`)
- **Arquitectura**: MVVM (Model-View-ViewModel) + Repository Pattern

---

## 📦 Compilación y Ejecución

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/Xmarcelo05/InventoryApp.git
   ```
2. Abrir el proyecto en Android Studio.
3. Compilar desde la terminal con Gradle:
   ```bash
   ./gradlew assembleDebug
   ```
4. Ejecutar en un emulador o dispositivo físico Android con API 24 o superior.
