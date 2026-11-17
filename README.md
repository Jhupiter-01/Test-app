# Hermes Bluetooth Test (Android)

Prueba experimental de audio de comunicación Bluetooth HFP/SCO con Redmi Watch 5 Lite y Honor 400.

## Compilación

1. Abrir esta carpeta en Android Studio (JDK 17 y Android SDK 35).
2. Esperar sincronización Gradle (Android Gradle Plugin 8.7.3).
3. Build > Build APK(s) o ejecutar en el Honor 400 por USB.
4. El APK se generará en `app/build/outputs/apk/debug/app-debug.apk`.

## Prueba

1. Emparejar reloj con teléfono y habilitar llamadas Bluetooth en la configuración del reloj.
2. Abrir app, conceder permisos.
3. Buscar dispositivos de comunicación y seleccionar el reloj si aparece.
4. Grabar y reproducir 5 segundos; revisar los dispositivos de entrada y salida informados.

## Interpretación

- Si el reloj no aparece, Android no lo expone como dispositivo de comunicación disponible para esta app en ese momento.
- Si aparece pero `setCommunicationDevice` falla, no se logró activar la ruta.
- Si la ruta de entrada o salida no es el reloj, la prueba no demuestra audio por reloj.
- Si ambas rutas son el reloj y se oye por él, hay base para crear el puente de Hermes.

No realiza llamadas, no usa números especiales y no transmite audio por internet. No se incluye APK precompilado porque este entorno no dispone del SDK de Android ni Gradle.
