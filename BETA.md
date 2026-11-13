# GUÍA Y CONDICIONES DE LA FASE BETA DE WYFOG
## Información para evaluadores y notas de la versión preliminar

¡Bienvenido al programa de pruebas beta de **Wyfog**!

Wyfog es un asistente y gestor integral de viajes diseñado con un enfoque **local-first** y **offline-first**, pensado para ofrecer control total, máxima autonomía sin conexión y seguridad sobre tus itinerarios, gastos y documentos.

Esta guía reúne todo lo necesario para instalar la versión preliminar, comprender sus capacidades actuales, conocer sus limitaciones y colaborar eficazmente en la detección de incidencias.

*Última actualización: Noviembre de 2026* • *Versión evaluada: v1.0.0+1 Beta*

---

### 1. ¿QUÉ SIGNIFICA QUE WYFOG ESTÉ EN FASE BETA?

La versión actual de Wyfog se encuentra en fase de desarrollo activo y pruebas de campo:
- **Evolución continua:** Las funciones principales están operativas y listas para su uso real, pero pueden sufrir ajustes en su diseño, ergonomía o arquitectura.
- **Riesgo de inconsistencias:** Podrían presentarse comportamientos anómalos en terminales con configuraciones de pantalla particulares o lentitud puntual en operaciones pesadas.
- **Cambios en base de datos:** Aunque Isar y la arquitectura de migraciones están preparadas para preservar los datos, durante fases beta siempre existe la posibilidad de que una actualización mayor requiera reestructurar esquemas locales.

> [!IMPORTANT]
> **Recomendación indispensable:** Realiza copias de seguridad periódicas de tus viajes mediante el botón **"Crear Respaldo" (.wyfogbackup)** antes y después de instalar actualizaciones de la beta.

---

### 2. PLATAFORMAS COMPATIBLES Y DISTRIBUCIÓN

Wyfog se distribuye en esta fase exclusivamente para dos sistemas operativos:

| Plataforma | Estado | Formato de Distribución | Requisitos Mínimos |
| :--- | :--- | :--- | :--- |
| **Android** | Beta Activa | Archivo APK instalable | Android 8.0 (API nivel 26) o superior. 3 GB de RAM recomendados. |
| **Windows** | Beta Activa | Instalador ejecutable (.exe) | Windows 10 (64 bits) versión 1809 o superior, o Windows 11. |

#### Plataformas no disponibles en esta fase:
- **iOS:** No disponible en esta fase del lanzamiento.
- **Web:** Excluida del lanzamiento actual de la aplicación. (La web pública asociada es únicamente un portal informativo de presentación).
- **macOS / Linux:** En evaluación para fases posteriores de desarrollo.

---

### 3. CÓMO INSTALAR Y CONFIGURAR LA VERSIÓN BETA

#### 3.1. En Android (Instalación de APK)
1. Descarga el paquete oficial `Wyfog-beta-v1.0.0-android.apk` desde la sección de publicaciones (*Releases*) autorizada.
2. Abre el archivo descargado en tu dispositivo.
3. Si el sistema te lo solicita, autoriza temporalmente a tu navegador o gestor de archivos para *"Instalar aplicaciones de fuentes desconocidas"*.
4. Sigue el asistente de instalación de Android y pulsa en **Abrir**.
5. **Permisos al primer arranque:** Durante el inicio de la aplicación y la bienvenida, Wyfog solicitará la activación de los permisos esenciales:
   - **Notificaciones:** Imprescindible para que suenen los recordatorios y avisos de vuelos o actividades de tu itinerario.
   - **Ubicación:** Para obtener tu posición GPS real en todo momento, calcular distancias exactas al buscar direcciones y centrar el mapa en el Modo en Vivo.
   - **Cámara:** Opcional, solicitada cuando decidas escanear un código QR para importar un viaje o tomar fotografías para tus recuerdos o perfil.
6. Configura tu PIN de seguridad propio de 6 dígitos cuando accedas por primera vez a la Bóveda Segura.

#### 3.2. En Windows (Escritorio)
1. Descarga el instalador oficial `Wyfog-beta-v1.0.0-windows.exe` desde las publicaciones oficiales.
2. Ejecuta el archivo descargado. Si Windows SmartScreen muestra un aviso de advertencia por tratarse de un ejecutable beta reciente sin reputación histórica acumulada, pulsa en *"Más información"* y a continuación en *"Ejecutar de todas formas"*.
3. Sigue los pasos del asistente de instalación para completar la instalación en tu equipo.
4. Abre Wyfog desde el menú Inicio o desde el acceso directo del escritorio.

---

### 4. COMPORTAMIENTO OFFLINE Y DEPENDENCIAS DE RED

Para sacar el máximo provecho a la aplicación y evitar sorpresas durante un viaje, ten muy presente cómo interactúa Wyfog con la red:

#### ¿Qué funciona 100% sin conexión a Internet?
- Crear, editar y consultar viajes y notas importantes.
- Organizar itinerarios detallados y alternar entre Plan A y Plan B.
- Consultar el **Modo en Vivo** durante el día de viaje.
- Recibir **alarmas y recordatorios exactos** de actividades en segundo plano (`USE_EXACT_ALARM`).
- Revisar y marcar la lista de equipaje.
- Registrar gastos en cualquier moneda y calcular balances entre compañeros (usando tasas guardadas o estáticas).
- Consultar la **Bóveda Segura** de documentos cifrados y reservas (con visor integrado a pantalla amplia y opción de abrir con otra aplicación).
- Ver el **Mapa Mundial** interactivo con las fronteras GeoJSON integradas y los países visitados (*Fog of War*).
- Compartir e importar viajes directamente entre dispositivos mediante **códigos QR** o archivos `.trip`.
- Generar y exportar archivos PDF (viaje, gastos, equipaje), descargar postales de recuerdos en **PNG con fondo transparente directamente en Galería** y exportar calendarios ICS.
- Generar y restaurar copias de seguridad `.wyfogbackup` (combinando o reemplazando).

#### ¿Qué requiere conexión a Internet o preparación previa?
- **Visualización de Mapas:** Wyfog utiliza teselas de OpenStreetMap. **No almacena el mapa de todo el planeta offline**. Para ver mapas sin conexión en tu destino, debes **descargar previamente la zona** desde la opción de mapas del viaje o navegar por la zona estando conectado para que las teselas se almacenen en la caché local persistente.
- **Búsqueda de Sitios y Geocodificación:** La búsqueda predictiva de calles o monumentos (Nominatim) y la localización de restaurantes cercanos (Overpass) consultan servidores en línea.
- **Previsión del Tiempo:** Obtener el pronóstico meteorológico actualizado (Open-Meteo) requiere conexión en el momento de la consulta.
- **Actualización de Tasas de Cambio:** Obtener tipos de cambio frescos (Frankfurter API / BCE) requiere conexión puntual; si estás desconectado, se aplicarán las últimas tasas guardadas o los valores de respaldo de la app.

---

### 5. PRECAUCIONES CON DOCUMENTOS, COPIAS Y SEGURIDAD

1. **Cifrado Fuerte de Documentos:** La Bóveda Segura cifra los archivos con **AES-256-GCM / CBC** y custodia la clave en el almacén seguro del sistema (`Keystore` / `Windows Credential Manager`).
2. **Separación de PIN:** La autenticación biométrica de Wyfog valida estrictamente tu huella o reconocimiento facial sin caer en la contraseña del teléfono. Si optas por usar PIN, utiliza el PIN de 6 dígitos configurado en Wyfog. Memorízalo bien, ya que los desarrolladores carecen de claves maestras para recuperarlo.
3. **Copias de Seguridad con o sin PIN:**
   - Wyfog te permite generar copias `.wyfogbackup` con PIN (derivado PBKDF2/SHA-256) o sin PIN.
   - Si tu aplicación contiene documentos sensibles en la Bóveda y seleccionas la opción de copia sin PIN, el sistema te mostrará una **advertencia de seguridad explícita** para que confirmes tu decisión de forma consciente.
4. **Restauración y Fusión de Viajes:** Al restaurar una copia, puedes elegir reemplazar todos los datos o **combinar con los existentes**, resolviendo cualquier coincidencia de nombres o viajes duplicados sin errores en la base de datos.
5. **Documentos originales:** En viajes internacionales, mantén siempre copias físicas de tus pasaportes, pólizas de seguro médico y visados. Wyfog es un asistente digital complementario.

---

### 6. CÓMO COMUNICAR ERRORES Y PROPUESTAS DE MEJORA

Tus comentarios son vitales para llevar Wyfog a su versión estable final. Dispones de dos vías de colaboración:

#### 📝 Vía Rápida y Recomendada: Formulario de Feedback (Sin Registro)
Para dejarnos impresiones generales, ideas de nuevas funciones o reportar un error sin necesidad de tener cuenta:
👉 [**Abrir Formulario de Feedback y Errores de Wyfog (Tally)**](https://tally.so/r/zEygb8) *(Toma menos de 1 minuto y no requiere crear cuentas)*.

#### 🐙 Vía Técnica: Incidencias en GitHub (Issues)
Si eres desarrollador o deseas hacer seguimiento detallado de un problema técnico, abre una incidencia en la pestaña de [**Issues**](https://github.com/JulioMV23/Wyfog/issues) del repositorio oficial de Wyfog.

##### Información recomendada para incluir en tu reporte técnico:
1. **Título descriptivo:** Ejemplo: *"[Android 14] Alarma de itinerario no suena a la hora programada"*.
2. **Dispositivo y Sistema Operativo:** Marca y modelo de teléfono, versión de Android o versión exacta de Windows (ej. Windows 11 Pro 23H2).
3. **Versión de Wyfog:** Consulta la versión en Ajustes > Información (ej. v1.0.0+1 Beta).
4. **Pasos para reproducir el fallo:** Secuencia numerada y precisa de lo que hiciste antes de que ocurriera el problema.
5. **Comportamiento esperado vs. Comportamiento obtenido.**
6. **Capturas de pantalla:** **RECORDATORIO:** Asegúrate de tachar o no incluir datos privados, fotos familiares, números de pasaporte o información sensible antes de subir cualquier imagen.

---

<div align="center">
  <p>© 2026 <strong>JUDMAV</strong> • Documentación Beta de Wyfog</p>
</div>
