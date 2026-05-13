# WebToApp - Modern WebView for Android

WebToApp es una plantilla moderna y minimalista para convertir cualquier sitio web en una aplicación Android nativa utilizando **Jetpack Compose** y **Material 3 Expressive**.

## 🚀 Características
- **Jetpack Compose:** UI moderna y reactiva.
- **Material 3 Expressive:** Lo último en diseño de Google.
- **Floating Header:** Barra de herramientas flotante con modo oscuro/claro.
- **WebView Avanzado:** Soporte para JavaScript, DOM Storage y Cache.
- **GitHub Workflows:** Automatización para generar APK y AAB de forma manual.
- **Kotlin First:** Estructura limpia usando solo Kotlin (carpeta `kotlin/`).

---

## 🛠️ Guía de Personalización

### 1. Cambiar el Nombre de la Aplicación
Abre `app/src/main/res/values/strings.xml` y cambia el valor de `app_name`:
```xml
<string name="app_name">Tu Nuevo Nombre</string>
```

### 2. Cambiar la URL del WebView
Abre `app/src/main/kotlin/com/example/webtoapp/MainActivity.kt` y busca la función `MainScreen`. Cambia la URL en la llamada a `WebViewComponent`:
```kotlin
WebViewComponent(url = "https://tu-sitio-web.com")
```

### 3. Cambiar el Paquete (Package Name)
1. Cambia el `namespace` y `applicationId` en `app/build.gradle.kts`.
2. Refactoriza la estructura de carpetas en `app/src/main/kotlin/` para que coincida con tu nuevo paquete.
3. Actualiza el `AndroidManifest.xml` si es necesario.

### 4. Cambiar Versión y Código de Versión
Abre `app/build.gradle.kts` y modifica:
```kotlin
versionCode = 2
versionName = "1.1.0"
```

### 5. Configurar Redes Sociales
En `MainActivity.kt`, busca la función `FloatingHeader`. Dentro del `DropdownMenu`, puedes añadir o quitar `DropdownMenuItem`:
```kotlin
DropdownMenuItem(
    text = { Text("Mi Red Social") },
    onClick = { 
        // Lógica para abrir link
        showMenu = false 
    },
    leadingIcon = { Icon(Icons.Default.Share, contentDescription = null) }
)
```

### 6. Cambiar Iconos (Mipmap)
Para cambiar el icono de la app:
1. Genera tus iconos usando una herramienta como [Android Asset Studio](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html).
2. Descarga el zip y reemplaza las carpetas `mipmap-*` en `app/src/main/res/`.
---

## 💰 Monetización con AdMob

La app ya incluye integración de anuncios **Intersticiales** y cumple con las políticas de privacidad (GDPR/UMP).

### 1. Configuración de IDs (Producción)
Para publicar, reemplaza los IDs de prueba en los siguientes lugares:

- **App ID:** En `app/src/main/AndroidManifest.xml`, cambia el valor de `com.google.android.gms.ads.APPLICATION_ID`.
- **Ad Unit ID (Intersticial):** En `app/src/main/kotlin/com/example/webtoapp/MainActivity.kt`, dentro de la función `loadInterstitial()`.

### 2. Cumplimiento Legal y Consentimiento
He integrado el SDK de **User Messaging Platform (UMP)** de Google, el cual:
- Muestra automáticamente el formulario de consentimiento en regiones donde es obligatorio (como Europa).
- Solo inicializa los anuncios si el usuario otorga el permiso.
- Cumple con las políticas actuales de la Play Store para anuncios personalizados.

---

## 🏗️ Workflows de GitHub
...

Este repositorio incluye dos flujos de trabajo manuales:
1. **Build Debug APK:** Genera un archivo `.apk` para pruebas rápidas.
2. **Build Release AAB:** Genera un archivo `.aab` (Android App Bundle) listo para subir a Play Store (sin firmar).

Para ejecutarlos:
Go to **Actions** > Select Workflow > **Run workflow**.

---

## 📋 Requisitos
- **JDK 21** (OpenJDK 21 recomendado).
- **Android SDK 24+** (Min SDK).
- **Gradle 8.7+**.

---
*Creado para mi blog de desarrollo Android.*
